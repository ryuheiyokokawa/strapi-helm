# Strapi on Kubernetes using Helm
Super basic helm chart for how you might deploy Strapi to Kubernetes.
Please be sure to modify the values.yaml or use helmfile or something similar.
For simplicity's sake, you can alway copy the values.yaml to values.prod.yaml too.

## Why did I make this?
Strapi doesn't exactly deploy super well on Kubernetes without a persistent storage so this shows how you can do it with an NFS mount.  BTW, this is mostly for demo use so use with your own caution.

## I don't want to use NFS
If you want to change the NFS mount to something else, it's very easy. You'll want to fork this and change out the strapi-pv.yaml file.  Just make sure your persistent storage is `ReadWriteMany` if you want it to be accessible from multiple nodes.  Here's a link for you: https://kubernetes.io/docs/concepts/storage/persistent-volumes/#access-modes

## Where is the docker image for Strapi that I'm supposed to use with this?
https://github.com/ryuheiyokokawa/strapi-docker
You can make a private registry or upload it wherever you want to.  I just changed a few things and I encourage you to fork that one too.  You'll need to do that if you want to add plugins and such from Strapi at the time of setup.

## I want this to do X, Y, and Z
Just go use helm on your own. Here's the docs: https://helm.sh/docs/