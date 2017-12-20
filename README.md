# Kubernetes Appliances


<img src="https://avatars3.githubusercontent.com/u/34630865?s=200&v=4" width="100">

----

Kubernetes appliances are open-source packages that simplify the deployment of self-contained highly-available (HA) applications you can use as BYO SaaS.

## Why Use Appliances?
Appliances guarantee a low-maintenance, highly-available SaaS package for just about any web service you can run in a cluster.

Sometimes a product you want to isolate isn't available as a managed service. Other services aren't designed for redundancy or HA and require additional architecture or application logic to be redundant and reliable.

Appliances solve both of these problems by creating a self-contained service with load balanced, sharded, or otherwise redundant pods inside. Some applications converted into appliances use their own distributed computing logic, while others require a thin logical layer to orchestrate individual pods.

The end result is a black-box SaaS appliance which offers all the functionality of its constituent service proxied through one or more network ports.

## Deploying
K8S appliances are based on [Helm charts](https://github.com/kubernetes/charts). As such, most of them can be launched just like any other chart.

## Creating
If you can load balance an application or run it in a distributed manner, you can turn it into an appliance. There are a few things you should keep in mind before getting started:

### Best Practices
* Appliances are self-sustaining wherever possible
* Appliances are based on Helm charts
* Custom images should be registered through a public Docker registry
* Expose any commonly configurable variable through values.yaml
* Honor the original service's API whenever possible
* Make all relevant logs visible to Helm
* Be cloud-agnostic and runnable on any K8S deployment
* Exposed services should be internal (VPC-only) by default unless clearly labeled otherwise
* Access to administrative ports or extra services should be configured in values.yaml

### Your First Appliance
1. Clone the appliance chart repository
1. Copy the chart template to a new directory
1. Build the chart to fit your needs
1. Build and deploy the Docker image to a service like quay.io


## Final Thoughts
Appliances are not a panacea, but they effectively fill the need for services not currently available as HA SaaS from various cloud providers. Technical knowledge of the software within an appliance is still important even though it is designed to be self-sustaining.
