FROM quay.io/operator-framework/helm-operator:v1.25
MAINTAINER Turbonomic <turbodeploy@turbonomic.com>

# Required OpenShift Labels
LABEL name="Prometurbo Operator" \
      vendor="Turbonomic" \
      version="8" \
      release="6" \
      summary="This is the prometurbo operator." \
      description="This operator will deploy an instance of prometurbo." \
### Required labels above - recommended below
      url="https://www.turbonomic.com" \
      io.k8s.description="Turbonomic Workload Automation Platform simultaneously optimizes performance, compliance, and cost in real-time. Workloads are precisely resourced, automatically, to perform while satisfying business constraints.  " \
      io.k8s.display-name="Prometurbo Operator" \
      io.openshift.expose-services="" \
      io.openshift.tags="turbonomic, Multicloud Container"

USER root
RUN microdnf update -y krb5-libs
USER ${USER_UID}

# Required Licenses
COPY licenses /licenses

COPY watches.yaml ${HOME}/watches.yaml
COPY helm-charts/ ${HOME}/helm-charts/
