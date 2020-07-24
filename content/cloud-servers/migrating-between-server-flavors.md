---
permalink: migrating-between-server-flavors/
audit_date:
title: 'Migrating Between Server Flavors'
type: article
created_date: '2020-07-d3'
created_by: Brian Abshier
last_modified_date:
last_modified_by:
product: Cloud Servers
product_url: cloud-product
---

Within the Rackspace Cloud, there are different flavors of server available to you. 
You can view the list [here](https://developer.rackspace.com/docs/cloud-servers/v2/general-api-info/flavors/) if you are unfamiliar.

You may reach a point where you've outgrown your server and need more resources. 
In such cases, the best option is to scale horizontally by cloning your server(s) and placing them behind something like a Load Balancer. Horizontal scaling, in most cases, is a better option than vertical scaling. 
The reason for this is that instead of having to take your server offline while you’re resizing up to larger one, horizontal scaling allows your existing pool of servers to remain online, serving traffic, while you're creating additional clones to offload some of that traffic to.

However, as mentioned, horizontal scaling may not be applicable to your case - or you may just not want to. In most cases, the server in question is a 30GB Standard (or Classic) flavor, or an 8GB General Purpose server. These flavors default to using Local Disks rather than the Block Storage volumes as their boot disk, and so can make it unclear how to move to a flavor which boots from a volume like Compute or Memory. 

### Limitations

Cloud images created from large servers don’t allow you to simply take an image and create a bootable Block Storage Volume. 
If the cloud server from which the image was taken has a root disk, or if the image has a `min_disk` parameter larger than 127 GB, you can’t create a volume from that image. This means that if you're using a 4GB Standard/Classic, an 8GB General Purpose server, or anything larger, you fall into this category. The reason behind this is that the component used to attach images to cloud servers, `qemu-img`, can’t handle files 127 GB or larger. Such an attempt results in an `HTTP 412 invalid image` error when performed through the API.


### Moving to Another Flavor

If your server does not fit into the category of the servers listed above, you should be able to take an image of your server, and create a Bootable Volume which you can use to boot the Compute or Memory flavor servers from. 
The documentation on how to do this is given in detail here:  [Boot a server from a Cloud Block Storage volume](https://support.rackspace.com/how-to/boot-a-server-from-a-cloud-block-storage-volume/)

However, if your server falls under the category listed in the Limitations section above, you'll have to perform a manual cloud-to-cloud migration of the server's data in order to move to the other flavor. This process is covered in our excellent document [Cloud-to-cloud migration](https://support.rackspace.com/how-to/cloud-to-cloud-migration/).
