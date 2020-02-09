---
layout: post
title: "Authentication using Okta API in Node.js"
categories: [NodeJS, Okta]
comments: true
---

I am currently working on a project which involves implementing authentication using API's of various 
identity providers. This is a code example of authentication using Okta in Node.js.

* I am using the path '/login/okta' with POST method.
* You can refer to the Okta documentation to login using authentication API here:
    [Okta Authentication API](https://developer.okta.com/docs/reference/api/authn/#request-parameters-for-primary-authentication)
* For the response parameters we need a username and password.
* OKTA_APP_URI is the url of our Okta application.
* After authentication via Okta, I am using the profile information in the body of the response and expiry date returned
    via Okta to create a [JWT](https://jwt.io/) token.

```javascript

router.post('/login/okta', async function(req, res, next) {
  const username = req.body.username;
  const password = req.body.password;

  if (!username || !password) {
    res.status(400).json({
      message: 'name or password missing - both must be supplied for login'
    });
  } else {
    request.post(OKTA_APP_URI, {
      json: {
        username: username,
        password: password,
        options: {
          multiOptionalFactorEnroll: true,
          warnBeforePasswordExpired: true
        }
      }
    }, (error, resp, body) => {
      if (error) {
        console.error(error);
      } else {
        if (resp.statusCode === 401) {
          res.status(401).json({
            message: 'Invalid password or user name'
          });
        } else if (resp.statusCode === 200) {
          let userProfile = body['_embedded']['user']['profile'];
          let expiry = Date.parse(body['expiresAt']);
          let payload = {
            iss: "org_name", //can assign from env var
            sub: "auth.api", //can assign from env var
            jti: uuid4(),
            exp: expiry,
            claims: {
              firstName: userProfile.firstName,
              lastName: userProfile.lastName,
              username: userProfile.login
            }
          };

          let token = jwt.sign(payload, jwtOptions.secretOrKey, {
            algorithm: jwtOptions.algorithm
          });
          res.status(200).json({
            message: 'Login was successful',
            "token": token
          });
        } else {
          res.json({
            message: 'Please refer to Okta error codes and description:\\' +
                '\"https://developer.okta.com/docs/reference/error-codes/#example-errors-listed-by-http-return-code\\"'
          })
        }
      }
    });
  }
});

```

Hope this helps someone. If you have any questions, feel free to comment below!
