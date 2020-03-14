---
layout: post
title: "Custom Links within ActiveAdmin Pages - Ruby on Rails"
categories: ['Ruby on Rails']
comments: true
author: alisha
image: assets/images/ruby.png
---

I am working on a Ruby on Rails project in my organization and I am very new to Rails. It took me days to find a way for creating custom buttons and their methods alongside the default 'Edit, View, Delete .....' buttons.

I finally found a fix to this and I concluded that Rails does really magical stuff behind the scenes which isn't obvious to a new programmer.

So, to give an overview of my task -- I am working on creating an 'Instances' tab on the ActiveAdmin index page. This instance page will list all of the current available AWS EC2 instances, and a link to VIEW, EDIT, DELETE (already available ones), STOP and REBOOT (custom ones, which I needed to make).

This is how my page looks after adding the custom links:

![pizze]({{ site.url }}/assets/ruby.png)

Oh and I removed the 'EDIT' link, I will show this as well. This one is pretty straighforward though.

So for adding the custom links:

```ruby
index do
      selectable_column
      id_column
      column :image_id
      column :min_count
      column :max_count
      column :monitoring
column() { |instance| link_to 'Stop', stop_admin_instance_path(instance), method: :post }
column() { |instance| link_to 'Reboot'}
      actions
end
```

We are creating these links in the seperate columns, with the name 'Stop', redirect path as "/admin/instances/stop", which Rails already has a helper for, nameOfMethod_admin_pageName_path(your_record), and the request method (GET/POST/PUT/DELETE). Similarly, it goes for 'Reboot' a well. To check this helper route, run rake routes from the console.

Now, we will add the method for stop button, which goes like this:

```ruby
member_action :stop, method: :post do
       instance = Instance.find(params[:id])
       AwsService.stop_ec2_instance(instance.instance_id)
       redirect_to "/admin/instances/"
end
```

I have made an AWS Service to stop the instances, using aws-ruby sdk, but that's out of the scope of this post.

params(:id) will send the id of the record on which this method would be called, to the find method, to find this record from the table and then the further instructions will be carried out on the record.

And to remove the default edit link, I did as follows:

```ruby
controller do
        actions :all, :except => [:edit]
end
```

Basically, in the controller section, you specify that all actions take place except the edit one'. If you wanted to remove, for example, delete action, you would just have to add delete similarly as the edit action.

I hope this would help someone :)