# Argo Workflows

This folder covers all the basic examples needed to understand and run argo workflows. These are taken directly from:
https://github.com/argoproj/argo-workflows/blob/master/examples/README.md#hello-world

Run the examples in the following order:
1. hello-world.yaml
2. parameters.yaml
3. steps.yaml
4. dag.yaml
5. artifacts

In case you want to follow along with this walkthrough, here's a quick overview of the most useful argo command line interface (CLI) commands.

```
argo submit hello-world.yaml    # submit a workflow spec to Kubernetes
argo list                       # list current workflows
argo get hello-world-xxx        # get info about a specific workflow
argo logs hello-world-xxx       # print the logs from a workflow
argo delete hello-world-xxx     # delete workflow
argo watch hello-world-xxx      # Watch a workflow
```

You can also run workflow specs directly using kubectl but the Argo CLI provides syntax checking, nicer output, and requires less typing.

```
kubectl create -f hello-world.yaml
kubectl get wf
kubectl get wf hello-world-xxx
kubectl get po --selector=workflows.argoproj.io/workflow=hello-world-xxx --show-all  # similar to argo
kubectl logs hello-world-xxx-yyy -c main
kubectl delete wf hello-world-xxx

```