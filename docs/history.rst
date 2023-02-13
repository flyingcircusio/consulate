Version History
===============
 
1.1.0a2 (unreleased)
~~~~~~~~~~~~~~~~~~~~

- Nothing changed yet.


1.1.0a1 (2023-02-13)
~~~~~~~~~~~~~~~~~~~~

- Nothing changed yet.


1.1.0+fc3 (2023-02-13)
~~~~~~~~~~~~~~~~~~~~~~

- Nothing changed yet.


1.1.0+fc2 (2023-02-06)
~~~~~~~~~~~~~~~~~~~~~~

- Fix support for Python 3.10+
- Revert (accidental?) package name change.

1.1.0+fc1 (2023-02-06)
~~~~~~~~~~~~~~~~~~~~~~

    - Removed support for Python 2.6 which has been EOLed since 2013
    - Removed the deprecated (since 0.3) `consulate.Session` handle
    - Changed :meth:`~consulate.Consul.agent.check.register` to match the new API in Consul
    - Changed :meth:`~consulate.Consul.agent.checks` to return a :data:`dict` instead of a :data:`list`.
    - Changed :meth:`~consulate.Consul.agent.services` to return a :data:`dict` instead of a :data:`list`.
    - Changed :meth:`~consulate.Consul.agent.service.register` to match the new API in Consul and checks are now passed
        in as :class:`consulate.models.agent.Check` instances.
  - Other Changes:
    - Added :meth:`~consulate.Consul.agent.maintenance`, :meth:`~consulate.Consul.agent.metrics`,
      :meth:`~consulate.Consul.agent.monitor`, :meth:`~consulate.Consul.agent.reload`,
      :meth:`~consulate.Consul.agent.self`, and :meth:`~consulate.Consul.agent.token`
    - Added :meth:`~consulate.Consul.acl.bootstrap` and  :meth:`~consulate.Consul.acl.replication`
    - Added :meth:`~consulate.Consul.agent.service.maintenance` (#107) - `Dj <https://github.com/Beahmer89>_`
    - Fixed run_once wrong args + subprocess parsing (#65) - Anthony Scalisi
    - Fixed :meth:`~consulate.Consul.catalog.register` and :meth:`~consulate.Consul.catalog.deregister` (#59)
    - Add support for ``flags``, ``cas``, and ``value`` in :meth:`Consulate.kv.acquire_lock` (#63)
    - Add ``--pretty`` option to kv backup (#69) - Brian Clark
    - Don't try to b64decode null values on kv restore (#68, #70) - Brian Clark
    - Raise server-error exception when setting a key fails due to a server error (#67) - Fredric Newberg
    - Address Python 2.6 incompatibility with the consulate cli and null data (#62, #61) - Wayne Walker
    - Added :class:`~consulate.api.lock.Lock` class for easier lock acquisition
    - New CLI feature to backup and restore ACLs (#71)
    - Added support for node metadata in :class:`consulate.Consul.api.catalog` & :class:`~consulate.Comsul.api.health` 

 - 0.6.0 - released *2015-07-22*
  - Added --recurse and --trim to cli kv_get (#58) - Matt Walker
  - Add run-once functionality to CLI (#57) - Harrison Dahme
  - Fix cli kv ls -l to report empty key lengths as 0 (#55) - Matt Walker
  - Add ability to restore from API output (#53) - Morgan Delagrange
  - If specified, use CONSUL_RPC_ADDR as defaults for API scheme/host/port in CLI app (#50) - Mike Dougherty
  - Fix a recursion introduced in 0.5.0 with catalog.register (#49)
  - Unix socket support moved to extras install, no longer required (#48) - Anders Daljord Morken
  - Add support for HTTP health checks and CLI support for deregistering services (#47) - Anders Daljord Morken
  - Handle an edge case where argparse doesn't properly pass int values (#45)
  - Handle binary data properly (#41)
  - Add --base64 flag to kv backup/restore for backing up and restoring binary data (#41)
  - Fix status.peers() returning string instead of list if only one peer exists (#39)
  - Remove print debugging on error message (#37) - Christian Kauhaus
  - Added additional test coverage
  - Expose consulate.exceptions.* at consulate package level
  - consulate.exceptions.ACLForbidden renamed to consulate.exceptions.Forbidden
  - Fix content encoding issues with Python 3
 - 0.5.1 - released *2015-05-13*
  - Fix a regression with consualte cli introduced with UnixSockets (#36) - Dan Tracy
 - 0.5.0 - released *2015-05-13*
  - Add ability to talk to Consul via Unix Socket
  - Remove the automatic JSON deserialization attempt of KV values
  - Add timeout parameter when creating the consulate.Consul instance (#31) - Grzegorz Śliwiński
  - Add ability to specify a different request adapter when creating a consulate.Consul instance (#30)
  - Add a flag that will prevent consulate.KV.set_record from replacing a pre-existing value (#29) - Jakub Wierzbowski
  - Add a flag to the consulate cli for the restore command to prevent the replacement of pre-existing values (#29) - Jakub Wierzbowski
  - Add query args to consulate.Health.service (#27) - Chen Lei
  - Removed the ability to override the datacenter in consulate.Session APIs
  - Address UTF-8 decoding/encoding issues with Python 3
  - Remove optional simplejson use
  - Remove default value arg for consulate.KV.get_record
  - General code cleanup and reduction of duplicate code
 - 0.4.0 - released *2015-03-14*
  - Major internal restructure and code cleanup
  - consulate.Session renamed to consulate.Consul
  - Fix issues regarding UTF-8 values
  - Fix usage of CAS for KV.set (#15)
  - Added new ``consulate`` kv options: ls, mkdir, rm (#16)
  - Add support for KV.get raw
  - Add ACL endpoint support
  - Add Session endpoint support
  - Add Event endpoint support
  - Added KV lock support (acquire, release)
  - Remove all remaining fragments of Tornado support
- 0.3.0 - released *2015-03-03*
  - Fix issues with quoting and UTF-8 in ``consulate kv backup/restore`` (#6, #8,
  - Fix installation issues related to missing tornado dependency (#10,
  - Make simplejson requirement optional
- 0.2.0 - released *2014-07-22*
  - Extract the ``passport`` app to a standalone library
- 0.1.2 - released *2014-05-06*
  - consulate cli app bugfixes
- 0.1.0 - released *2014-05-06*
  - Initial release
