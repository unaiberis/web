================================
Web Datetime Picker Default Time
================================

.. 
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! This file is generated by oca-gen-addon-readme !!
   !! changes will be overwritten.                   !!
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! source digest: sha256:a5ffb697bdf4c26817212f783a9d4d617e91fcdc912a7750382d3eddaff05f7b
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

.. |badge1| image:: https://img.shields.io/badge/maturity-Beta-yellow.png
    :target: https://odoo-community.org/page/development-status
    :alt: Beta
.. |badge2| image:: https://img.shields.io/badge/licence-AGPL--3-blue.png
    :target: http://www.gnu.org/licenses/agpl-3.0-standalone.html
    :alt: License: AGPL-3
.. |badge3| image:: https://img.shields.io/badge/github-OCA%2Fweb-lightgray.png?logo=github
    :target: https://github.com/OCA/web/tree/16.0/web_datetime_picker_default_time
    :alt: OCA/web
.. |badge4| image:: https://img.shields.io/badge/weblate-Translate%20me-F47D42.png
    :target: https://translation.odoo-community.org/projects/web-16-0/web-16-0-web_datetime_picker_default_time
    :alt: Translate me on Weblate
.. |badge5| image:: https://img.shields.io/badge/runboat-Try%20me-875A7B.png
    :target: https://runboat.odoo-community.org/builds?repo=OCA/web&target_branch=16.0
    :alt: Try me on Runboat

|badge1| |badge2| |badge3| |badge4| |badge5|

This module customizes the datetime picker widget and allows to define a
default time to be applied in case the user selects only a Date.

For example, if a user wants to define a commitment date without having
to specify the time on that date, setting the default time value on the
field in the Form view allows to ensure the commitment date will be set
to this time instead of the time when the page was loaded by the
browser.

**Table of contents**

.. contents::
   :local:

Usage
=====

You can define the default time as follows for a static value:

.. code:: xml

       <field name="your_datetime_field" options="{'defaultTime': {'hour': 8, 'minute': 30, 'second': 15 }}"/>

Otherwise you can also use a JSON field to make it dynamic through a
compute function, and reference this field in the view:

.. code:: python

      start_time = field.Json(compute="_compute_start_time")

      def _compute_start_time(self):
          for rec in self:
              rec.start_time = {'hour': 8, 'minute': 30, 'second': 15 }

.. code:: xml

      <field name="start_time" invisible="1" />
      <field name="your_datetime_field" options="{'defaultTime': 'start_time'}"/>

Known issues / Roadmap
======================

-  Handle Timezone related to the default time

Bug Tracker
===========

Bugs are tracked on `GitHub Issues <https://github.com/OCA/web/issues>`_.
In case of trouble, please check there if your issue has already been reported.
If you spotted it first, help us to smash it by providing a detailed and welcomed
`feedback <https://github.com/OCA/web/issues/new?body=module:%20web_datetime_picker_default_time%0Aversion:%2016.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Do not contact contributors directly about support or help with technical issues.

Credits
=======

Authors
-------

* Camptocamp

Contributors
------------

-  Akim Juillerat akim.juillerat@camptocamp.com
-  Iván Todorovich ivan.todorovich@camptocamp.com

Maintainers
-----------

This module is maintained by the OCA.

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

.. |maintainer-grindtildeath| image:: https://github.com/grindtildeath.png?size=40px
    :target: https://github.com/grindtildeath
    :alt: grindtildeath

Current `maintainer <https://odoo-community.org/page/maintainer-role>`__:

|maintainer-grindtildeath| 

This module is part of the `OCA/web <https://github.com/OCA/web/tree/16.0/web_datetime_picker_default_time>`_ project on GitHub.

You are welcome to contribute. To learn how please visit https://odoo-community.org/page/Contribute.
