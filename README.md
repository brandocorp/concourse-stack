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
