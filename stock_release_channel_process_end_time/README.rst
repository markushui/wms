======================================
Stock Release Channel Process End Date
======================================

.. 
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! This file is generated by oca-gen-addon-readme !!
   !! changes will be overwritten.                   !!
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! source digest: sha256:6870d2ff3e9d5c184e2c5f5758431740153119d4f322bbdb24b32664f60ef83e
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

.. |badge1| image:: https://img.shields.io/badge/maturity-Beta-yellow.png
    :target: https://odoo-community.org/page/development-status
    :alt: Beta
.. |badge2| image:: https://img.shields.io/badge/licence-AGPL--3-blue.png
    :target: http://www.gnu.org/licenses/agpl-3.0-standalone.html
    :alt: License: AGPL-3
.. |badge3| image:: https://img.shields.io/badge/github-OCA%2Fwms-lightgray.png?logo=github
    :target: https://github.com/OCA/wms/tree/16.0/stock_release_channel_process_end_time
    :alt: OCA/wms
.. |badge4| image:: https://img.shields.io/badge/weblate-Translate%20me-F47D42.png
    :target: https://translation.odoo-community.org/projects/wms-16-0/wms-16-0-stock_release_channel_process_end_time
    :alt: Translate me on Weblate
.. |badge5| image:: https://img.shields.io/badge/runboat-Try%20me-875A7B.png
    :target: https://runboat.odoo-community.org/builds?repo=OCA/wms&target_branch=16.0
    :alt: Try me on Runboat

|badge1| |badge2| |badge3| |badge4| |badge5|

This module allows to configure an end time on a release channel that will become the channel end date when the channel awakes. This process end date specify when all the work in the channel should be finalized.
Note: ensure to configure the timezone on the address of the warehouse to have the right time to datetime conversion.

The channel process end date can be propagated to the generated pickings in order to solve two challenges:

- You expect to view the stock pickings in the same order as the the one you
  have set as process end date on the release channel. This way you can easily
  manage the deliveries in the same order as the one expected by the planned
  release channels.

- You expect to set as deadline of your released move operations the process
  end date of the release channel. This is useful to ensure that move created
  when releasing deliveries get the same deadline as the one set on the
  release channel. This is also required to allow the merge of move operations
  generated for the same product, location in the same stock picking.


**Table of contents**

.. contents::
   :local:

Usage
=====

Assign the release channel's process end date to the pickings as scheduled date:

#. Assign a timezone on the Warehouse address if defined and if needed
   If you have a lot of warehouses in the same timezone, you can also define
   the timezone on the company partner.
   If you don't define a timezone on the warehouse(s) nor the company, the process
   end time on channels will be considered as UTC.
#. Propagate/update scheduled date of picking follow process end date/time automatically
   by setting "Update Scheduled Date" configuration in Settings/General Settings/Inventory

#. Go To Release Channels
#. Set an end time
#. Wake up the channel
#. The assigned pickings have their scheduled date set at the next end time. (if enabled "Update Scheduled Date" config)

When the assigned pickings are released, the move date deadline is set to the scheduled date
into the pickings generated by the release process.

Known issues / Roadmap
======================

* Maybe something to do on pickings level when setting channels asleep (storing
  the original scheduled date or ...).

Bug Tracker
===========

Bugs are tracked on `GitHub Issues <https://github.com/OCA/wms/issues>`_.
In case of trouble, please check there if your issue has already been reported.
If you spotted it first, help us to smash it by providing a detailed and welcomed
`feedback <https://github.com/OCA/wms/issues/new?body=module:%20stock_release_channel_process_end_time%0Aversion:%2016.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Do not contact contributors directly about support or help with technical issues.

Credits
=======

Authors
~~~~~~~

* ACSONE SA/NV
* BCIM

Contributors
~~~~~~~~~~~~

* Denis Roussel <denis.roussel@acsone.eu>
* Jacques-Etienne Baudoux (BCIM) <je@bcim.be>

Maintainers
~~~~~~~~~~~

This module is maintained by the OCA.

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

.. |maintainer-rousseldenis| image:: https://github.com/rousseldenis.png?size=40px
    :target: https://github.com/rousseldenis
    :alt: rousseldenis
.. |maintainer-jbaudoux| image:: https://github.com/jbaudoux.png?size=40px
    :target: https://github.com/jbaudoux
    :alt: jbaudoux

Current `maintainers <https://odoo-community.org/page/maintainer-role>`__:

|maintainer-rousseldenis| |maintainer-jbaudoux| 

This module is part of the `OCA/wms <https://github.com/OCA/wms/tree/16.0/stock_release_channel_process_end_time>`_ project on GitHub.

You are welcome to contribute. To learn how please visit https://odoo-community.org/page/Contribute.
