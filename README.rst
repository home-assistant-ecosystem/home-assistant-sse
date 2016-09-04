Home Assistant Server Sent Events
=================================

`Home Assistant <https://home-assistant.io>`__ ships its own very nice
web frontend. This prototype shows an option to display values without
the possibility of interacting with Home Assistant by the user.

A requirement on the client-side is existing support for the
[EventSource](https://developer.mozilla.org/en-US/docs/Web/API/EventSource)
interface. This means that not all browsers are supported.

Installation
------------
It's assumed that your Home Assistant installation is ready before cloning
this repository. Change to your local Home Assistant configuration folder
``.homeassistant`` and clone this repository.

.. code:: bash

    $ git clone https://github.com/fabaff/home-assistant-sse.git

In the folder ``www`` you will find an ``index.html`` file and the folder that
contains the CSS file.

Open the ``index.html`` file and include the entities you want to show on the
page in the ``entities`` array. Check the "Developer tools" of Home Assistant
to retrieve the entity ID. Please replace the periods (dots) with undersores
in the entities.

.. code:: javascript

    var entities = ['sensor_cpu',
                    'sensor_time',
                    'binary_sensor_printer',
                    'sensor_time_beat',
                    'sun_sun'
                    ];

Launch your Home Assistant instance.

.. code:: bash

    $ hass

Now the web site is available at http://[your_hass_host]:8123/local/index.html

Screenshot
----------

|screenshot|

License
-------
``home-assistant-sse`` is licensed under MIT, for more details check
LICENSE.

.. |screenshot| image:: https://raw.githubusercontent.com/fabaff/home-assistant-sse/master/ha-display1.png
   :target: https://github.com/fabaff/home-assistant-sse
