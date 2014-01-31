ubuntu-12.0.4-3.8
=================

Packer template for Ubuntu 12.0.4 image with the 3.8 kernel.

These EBS backed AMIs are available in:

1. us-west-2: ami-b4eb8a84
2. us-west-1: ami-560e3c13
3. us-east-1: ami-f702309e

You can also build a DigitalOcean Droplet or Rackspace OpenStack Image.

Ansible and Chef are installed as available provisioning systems.

In order to build an Amazon AMI, DigitalOcean Droplet or Rackspace OpenStack image, you will need accounts for each. Export these values to get Packer to honor them automatically:

    # Rackspace
    export SDK_USERNAME="username"  # Same as here: https://mycloud.rackspace.com/
    export SDK_PASSWORD="password-to-login" # Not the API key.
    export SDK_PROVIDER="rackspace-us" # Or rackspace-uk
    
    # EC2 - can be found here: https://portal.aws.amazon.com/gp/aws/securityCredentials?
    export AWS_ACCESS_KEY="long-random-string"
    export AWS_SECRET_KEY="another-even-longer-long-random-string"
    
    # Digital Ocean - get these here: https://cloud.digitalocean.com/api_access
    export DIGITALOCEAN_CLIENT_ID="long-random-string"
    export DIGITALOCEAN_API_KEY="another-long-random-string"

To build the images - use these Rakefile targets:

    rake build            # Build all Packer targets
    rake build_ami        # Build AMI
    rake build_droplet    # Build Droplet
    rake build_openstack  # Build Openstack Image
    rake build_vagrant    # Build Vagrant box

This template forms the base image for [octohost](http://www.octohost.io).