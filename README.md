Xpanse Python SDK
==================
.. image:: https://github.com/PaloAltoNetworks/cortex-xpanse-python-sdk/blob/main/docs/_source/_static/xpanse_banner.png?raw=true
   :width: 800
   :target: https://expanse.co/

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
   :target: https://github.com/psf/black

.. image:: https://img.shields.io/badge/python-3.6%20%7C%203.7%20%7C%203.8-blueviolet
   :target: https://pypi.python.org/pypi/xpanse

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
   :target: https://github.com/psf/black

.. image:: https://img.shields.io/pypi/l/xpanse
   :target: https://github.com/PaloAltoNetworks/cortex-xpanse-python-sdk/blob/main/LICENSE

.. image:: https://img.shields.io/github/contributors/PaloAltoNetworks/cortex-xpanse-python-sdk
   :target: https://github.com/PaloAltoNetworks/cortex-xpanse-python-sdk/graphs/contributors

Overview
--------

This library is intended to be an interface to the `Xpanse Expander API <https://knowledgebase.xpanse.co/expander-apis/>`_.

Install
-------
.. code-block:: python

    pip install xpanse

Requirements
------------

Python 3.6+

Usage
-----
`Documentation <https://cortex-xpanse-python-sdk.readthedocs.io/en/latest/>`_

.. code-block:: python

    # Import client
    from xpanse.client import ExClient

    # initialize client
    client = ExClient()

    # get ip_range iterator object and dump to a list
    ranges = client.assets.ip_range.list().dump()

You can view more example code in the `examples <https://github.com/PaloAltoNetworks/cortex-xpanse-python-sdk/tree/main/examples>`_ directory.

Configuration
-------------
A valid Client ID and Secret is required for use. This is recommended over using a JWT, as they have limited lifespans.
While a bearer token is supported in this version, this auth flow is being deprecated. Therefore, it is highly recommended to use Client Credentials.

RECOMMENDED
***********
You can supply them as environment variables using the variable names ``XPANSE_CLIENT_ID`` AND ``XPANSE_CLIENT_SECRET`` and/or ``XPANSE_JWT_TOKEN``.

.. code-block:: python

    export XPANSE_CLIENT_ID=<Client ID>
    export XPANSE_CLIENT_SECRET=<Client Secret>
    # or
    export XPANSE_JWT_TOKEN=<JWT>

[Deprecated]
A valid Bearer token or JWT is required for use. Bearer tokens are suggested as JWTs have a limited lifespan.

RECOMMENDED
***********
You can supply them as environment variables using the variable names ``XPANSE_BEARER_TOKEN`` and/or ``XPANSE_JWT_TOKEN``.

.. code-block:: python

    export XPANSE_BEARER_TOKEN=<Bearer Token>
    # or
    export XPANSE_JWT_TOKEN=<JWT>


Logging
-------
Logging is handled through the python logging package. To enable different levels of verbosity in your scripts you can do the following:

.. code-block:: python

    import logging
    logging.basicConfig(level=logging.DEBUG)

You can read more at `<https://docs.python.org/3/library/logging.html>`_.
