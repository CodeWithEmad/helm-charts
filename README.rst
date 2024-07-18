⚙ Maintenance Chart
===================

This Helm chart deploys a simple maintenance page using Caddy as the web server.
It's designed to be easily deployed when you need to take your service down for maintenance,
providing a user-friendly message to your visitors.

Features
--------

- Simple HTML maintenance page.
- Caddy web server for efficient serving of static content.
- Kubernetes Deployment, Service, and Ingress resources.
- Configurable maintenance message.

Prerequisites
-------------

- Kubernetes 1.19+
- Helm 3.2.0+
- Ingress controller (e.g., nginx-ingress) installed in your cluster.

How to use
----------

To install the chart with the release name ``my-maintenance``:

.. code-block:: bash

    helm install my-maintenance ./maintenance --set ingress.host=your-domain.com

This command deploys the maintenance page on the Kubernetes cluster with the default configuration.
The `--set` flag allows you to customize the ingress host.

To revert to your normal service, uninstall the maintenance chart and redeploy your original service.

.. code-block:: bash

    helm uninstall my-maintenance

This removes all the Kubernetes components associated with the chart and deletes the release.

Configuration
-------------

The following table lists the configurable parameters of the Maintenance chart and their default values.

+----------------------------+------------------------------------------+---------------------------+
| Parameter                  | Description                              | Default                   |
+============================+==========================================+===========================+
| ``replicaCount``           | Number of replicas                       | ``1``                     |
+----------------------------+------------------------------------------+---------------------------+
| ``namespace``              | Kubernetes namespace to use              | ``default``               |
+----------------------------+------------------------------------------+---------------------------+
| ``image.repository``       | Image repository                         | ``caddy``                 |
+----------------------------+------------------------------------------+---------------------------+
| ``image.tag``              | Image tag                                | ``2.6.2``                 |
+----------------------------+------------------------------------------+---------------------------+
| ``image.pullPolicy``       | Image pull policy                        | ``IfNotPresent``          |
+----------------------------+------------------------------------------+---------------------------+
| ``service.type``           | Kubernetes Service type                  | ``ClusterIP``             |
+----------------------------+------------------------------------------+---------------------------+
| ``service.port``           | Kubernetes Service port                  | ``80``                    |
+----------------------------+------------------------------------------+---------------------------+
| ``ingress.enabled``        | Enable ingress controller resource       | ``true``                  |
+----------------------------+------------------------------------------+---------------------------+
| ``ingress.className``      | IngressClass that will be be used        | ``nginx``                 |
+----------------------------+------------------------------------------+---------------------------+
| ``ingress.host``           | Hostname to your maintenance application | ``down.example.com``      |
+----------------------------+------------------------------------------+---------------------------+
| ``ingress.annotations``    | Additional ingress annotations           | ``{}``                    |
+----------------------------+------------------------------------------+---------------------------+
| ``ingress.tls.enabled``    | Enable TLS for ingress                   | ``false``                 |
+----------------------------+------------------------------------------+---------------------------+
| ``ingress.tls.secretName`` | Name of the TLS secret                   | ``""``                    |
+----------------------------+------------------------------------------+---------------------------+
| ``maintenance.title``      | Header title                             | See `values.yaml`_        |
+----------------------------+------------------------------------------+---------------------------+
| ``maintenance.message``    | Message displayed on the maintenance     | See `values.yaml`_        |
|                            | page                                     |                           |
+----------------------------+------------------------------------------+---------------------------+
|``maintenance.description`` | A short description below the message    | See `values.yaml`_        |
+----------------------------+------------------------------------------+---------------------------+
| ``maintenance.bannerURL``  | URL of an image showing on top of the    | See `values.yaml`_        |
|                            | message                                  |                           |
+----------------------------+------------------------------------------+---------------------------+
|``maintenance.faviconURL``  | URL of a ``favicon.ico`` file            | See `values.yaml`_        |
+----------------------------+------------------------------------------+---------------------------+


Specify each parameter using the ``--set key=value[,key=value]`` argument to ``helm install``.
For example:

.. code-block:: bash

    helm install my-maintenance ./maintenance \
      --set namespace=project-x \
      --set ingress.host="maintenance.mysite.com" \
      --set ingress.tls.enabled=true \
      --set ingress.tls.secretName="maintenance-mysite-com" \
      --set maintenance.message="We are performing scheduled maintenance. We'll be back online shortly!" \
      --set maintenance.caption="For more contact <a href='mailto:example@email.com'>example@email.com</a>"

If you want to issue a new certificate using something like ``cert-manager``, use:

.. code-block:: python

    --set ingress.annotations."cert-manager\.io/cluster-issuer"=letsencrypt

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart.
For example:

.. code-block:: bash

    helm install my-maintenance ./maintenance -f my-values.yaml


.. _values.yaml: https://github.com/codewithemad/maintenance-chart/blob/master/values.yaml

Contributing
------------

Contributions are welcome! Please see the `CONTRIBUTING.rst`_ file for details.

.. _CONTRIBUTING.rst: https://github.com/codewithemad/maintenance-chart/blob/master/CONTRIBUTING.rst

License
-------

This work is licensed under the terms of the `GNU Affero General Public License (AGPL) <https://github.com/codewithemad/maintenance-chart/blob/master/LICENSE>`_.
