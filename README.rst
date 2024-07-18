Helm Charts Repository
======================

This repository contains Helm charts for various applications and services.

Available Charts
----------------

* `maintenance`_: A chart for deploying a maintenance page.

.. _maintenance: https://github.com/CodeWithEmad/helm-charts/tree/master/charts/maintenance

Usage
-----

To use the charts from this repository, follow these steps:

1. Add the Helm repository:

   .. code-block:: bash

      helm repo add codewithemad https://codewithemad.github.io/helm-charts/

2. Update your local Helm chart repository cache:

   .. code-block:: bash

      helm repo update

3. Install a chart:

   .. code-block:: bash

      helm install my-release codewithemad/<chart-name>

For more details on each chart, please refer to the README file in the respective chart directory.

Contributing
------------

Contributions are welcome! Please see the `CONTRIBUTING.rst`_ file for details.

.. _CONTRIBUTING.rst: https://github.com/codewithemad/helm-charts/blob/master/CONTRIBUTING.rst

License
-------

This work is licensed under the terms of the `GNU Affero General Public License (AGPL) <https://github.com/codewithemad/helm-charts/blob/master/LICENSE>`_.

Support
-------

If you encounter any problems or have any questions, please file an issue on the GitHub repository.