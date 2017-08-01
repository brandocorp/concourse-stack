# Concourse CI Stack

Demonstration of a Fully-Featured Concourse CI Stack.

## Overview

The goal of this repo is to create an example for setting up a fully operational Concourse CI server stack. Concourse CI because of its notion of [resources][1]. Specifically, Concourse comes with support for custom resource types, allowing access to nearly anything your pipeline might need.

## Stack Components

### Concourse

#### Dependencies

 * PostgreSQL 9.3+
 * Vault

### PostgreSQL

#### Dependencies

 * None

### Vault

#### Dependencies

 * Consul

### Consul

#### Dependencies

 * None

## Preparing

### Chef Setup

#### ChefDK

Install the latest stable version of the [ChefDK](https://downloads.chef.io/chefdk/stable) on your workstation.

#### Knife Configuration

If you're an avid Chef user, then you'll likely already know what to do here. Otherwise, you can follow these instructions to run with a local setup:


1) Create your `knife.rb` file

```bash
touch .chef/knife.rb
```

```ruby
# See https://docs.getchef.com/config_rb_knife.html for more information on knife configuration options

current_dir = File.dirname(__FILE__)
log_level                :info
log_location             STDOUT
node_name                "chef-admin"
client_key               "#{current_dir}/chef-admin.pem"
local_mode               true
chef_zero.enabled        true
cookbook_path            ["#{current_dir}/../cookbooks"]
```

2) Generate a private key

```
ssh-keygen -t rsa -b 2048 -f .chef/chef-admin.pem -N ''
```

3) Test the configuration is valid

```bash
knife status
```

