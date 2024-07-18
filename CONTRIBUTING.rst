Contributing to the Maintenance Chart
=====================================

We welcome contributions to the Maintenance Chart!
This document outlines the process for contributing to this project.

Getting Started
---------------

1. Fork the repository on GitHub.
2. Clone your fork locally:

.. code-block:: bash

    git clone https://github.com/codewithemad/maintenance-chart.git
    cd maintenance-chart

3. Create a new branch for your feature or bug fix:

.. code-block:: bash

    git checkout -b feature/your-feature-name

Making Changes
--------------

1. Make your changes in your feature branch.
2. Update or add tests as necessary.
3. Update documentation, including `README.rst`_ and `CHANGELOG.rst`_, if applicable.
4. Ensure your code follows the project's style and best practices.

.. _README.rst: https://github.com/codewithemad/maintenance-chart/blob/master/README.rst
.. _CHANGELOG.rst: https://github.com/codewithemad/maintenance-chart/blob/master/CHANGELOG.rst

Testing Your Changes
--------------------

Before submitting a pull request, make sure to test your changes:

1. Run the Helm linter:

.. code-block:: bash

    helm lint ./maintenance

2. Perform a template rendering:

.. code-block:: bash

    helm template ./maintenance

3. Do a dry-run installation:

.. code-block:: bash

    helm install --dry-run --debug test ./maintenance

Submitting a Pull Request
-------------------------

1. Push your changes to your fork on GitHub:

.. code-block:: bash

    git push origin feature/your-feature-name

2. Go to the original repository on GitHub and create a new Pull Request.
3. Provide a clear description of the changes and reference any related issues.
4. Submit the Pull Request for review.

After Submitting
----------------

- Respond to any feedback on your Pull Request.
- If requested, make additional commits to your branch and push them.
- Once approved, your Pull Request will be merged into the main branch.

Reporting Issues
----------------

If you find a bug or have a suggestion for improvement:

1. Check if the issue already exists in the GitHub issue tracker.
2. If not, create a new issue, providing as much relevant information as possible.

Style Guide
-----------

- Follow the Helm best practices for chart development.
- Use clear, descriptive commit messages.
- Maintain consistent indentation and formatting.

Questions?
----------

If you have any questions about contributing, feel free to ask in the issue tracker.

Thank you for contributing!