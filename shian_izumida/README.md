## Template

- winkel
https://drive.google.com/file/d/1Z5Rn65_G2Rj-aywNsrlOjGPMmwrmSZYX/view

## Repos

- https://repl.it/@sianizm/sample-ec-site-static
- https://repl.it/@sianizm/sample-ec-site

## Static page

- [x] Add html to page
- [x] Add css to page
- [x] Add js to page
- [x] Custom index page
- [ ] Update other pages common parts: title, header, footer
- [x] Update content on index.html
- [ ] Update video, image
- [ ] Update links on all pages


## Dynamic Rails app

- [x] Initialize Rails
- [x] Root page
- [x] all other pages
- [ ] Dinamical



# Setup 

## Initial setting 
1. Fix config/application.rb

Add 
```
require 'rails/all'
```

Remove
```
require "rails"
# Pick the frameworks you want:
require "active_model/railtie"
require "active_job/railtie"
require "active_record/railtie"
require "active_storage/engine"
require "action_controller/railtie"
# require "action_mailer/railtie"
require "action_view/railtie"
# require "action_cable/engine"
# require "sprockets/railtie"
# require "rails/test_unit/railtie"

```

## Define static page
### root page
config/routes.rb
```
Rails.application.routes.draw do
  root :to => "home#index"
  # For details on the DSL available within this file, see http://guides.rubyonrails.org/routing.html
end
```
app/controllers/home_controller.rb
```
class HomeController < ApplicationController
  def show
  end
end

```
- put top page html inner <body> tag in app/views/home/index.html.erb
- put css & js information in app/views/layout/application.html.erb


- Define header 
- Define footer 


### Define other page
Define  products, product, cart, checkout same way with root page.


## Define dynamic page
Define migration, products `db/migrates/yyyymmddhhmm_create_products.rb`
```
class CreateProducts < ActiveRecord::Migration[5.1]
  def change
    create_table :products do |t|
      t.string :name
      t.integer :price
      t.text :description
      t.timestamps
    end
  end
end

```
- Apply instance variable for controller and view file
- To upload image, setup Active Storage https://edgeguides.rubyonrails.org/active_storage_overview.html#setup

