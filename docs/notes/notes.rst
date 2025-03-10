.. include:: ../03-exports/aliases-api.include

.. _release_notes:

Information about the release lifecycle can be found
`here <https://github.com/eProsima/Fast-DDS/blob/master/RELEASE_SUPPORT.md>`_.

Version 2.8.0
=============

This minor release includes several new features, performance improvements (especially in the case of topics with many
instances), CI improvements (including the ability to run the CI in Android emulators or devices), and several bug
fixes.

.. note::
    Mind that, even though this release is API compatible with previous v2.x versions, it is *NOT* ABI compatible with
    previous versions.
    This means that applications upgrading Fast DDS to v2.8.0 will require recompilation, though not source code
    modification.

.. note::
    It is also advisable to regenerate the type support from the IDL files using
    [Fast DDS-Gen v2.2.0](https://github.com/eProsima/Fast-DDS-Gen/releases/tag/v2.2.0).
    Furthermore, if upgrading to v2.8.0, it is also recommended to upgrade Fast CDR to
    [v1.0.25](https://github.com/eProsima/Fast-CDR/releases/tag/v1.0.25)

This release includes the following **features**:

1. Full :ref:`Ownership<ownershipqospolicy>` and :ref:`OwnershipStrength<ownershipstrengthqospolicy>` QoS support
2. External locators
3. UDPv6 support for :ref:`fast-discovery-server tool<cli_discovery>` and
   :ref:`ROS_DISCOVERY_SERVER<env_vars_ros_discovery_server>`
4. :ref:`XML configuration support for statistics DataWriters QoS<statistics_enable_datawriters>`
5. :ref:`SNI support<transport_tcp_tls>`
6. :ref:`Propagate PropertyQoS properties when explicitly set<propertypolicyqos>`
7. Add API to createRTPSWriter with a custom pool
8. Add :class:`std::string::compare` API to :class:`fixed_string`
9. Get WAN address API in TCPv4 transport descriptors
10. Adding :class:`DomainParticipantFactory::get_shared_instance()` API

This release includes the following **improvements**:

1. Performance improvements:
    1. Skip writer_removed processing for unaccounted instances
    2. Improve GUID_t operator< performance
2. CI improvements:
    1. Add optional parameters to thread-sanitizer job
    2. Enable Android testing on device
3. Examples:
    1. Update BasicConfigurationExample to allow set up TTL
    2. Add Guid info to BasicConfiguration Example :class:`cout`
4. Internal implementation improvements:
    1. Add script to generate idl files
    2. Group set_qos_from_attributes free functions into a separate file
    3. Update script for generating idl files
    4. Set :class:`last_heartbeat_count_` private member of WriterProxy as atomic
5. Android Improvements
6. Upgrade Fast CDR submodule

This release includes the following **bugfixes**:

1. Synchronization fixes:
    1. Fix datarace using writer's locator selectors
    2. Add lock guard at changing SHM port listener status members
    3. Add atomic variable to prevent datarace in FlowController
    4. Disable RTPSParticipantImpl after removing it from RTPSDomain participants list
    5. Fixing datarace on listener callbacks
    6. Protect access to reader listeners
    7. Use thread-safe localtime function in unix distributions
    8. Fixed usage of uninitialised ifreq
    9. Adding protection to id_counter access
2. Repository fixes:
    1. Fix spelling mistake
    2. Add python3 dependency to package.xml
3. Other:
    1. Fix null dereference on parseXMLBitsetDynamicType
    2. Change internal include path of nlohmann/json header file
    3. Instance allocation consistency
    4. Fix complex member printing for DynamicDataHelper
    5. Fix initialization order in mock
    6. Upgraded internal type supports

.. note::
  If you are upgrading from a version older than 1.7.0, it is **required** to regenerate generated source from IDL
  files using *fastddsgen*.
  If you are upgrading from any older version, regenerating the code is *highly recommended*.

Previous versions
=================

.. include:: previous_versions/v2.7.1.rst
.. include:: previous_versions/v2.7.0.rst
.. include:: previous_versions/v2.6.2.rst
.. include:: previous_versions/v2.6.1.rst
.. include:: previous_versions/v2.6.0.rst
.. include:: previous_versions/v2.5.2.rst
.. include:: previous_versions/v2.5.1.rst
.. include:: previous_versions/v2.5.0.rst
.. include:: previous_versions/v2.4.2.rst
.. include:: previous_versions/v2.4.1.rst
.. include:: previous_versions/v2.4.0.rst
.. include:: previous_versions/v2.3.5.rst
.. include:: previous_versions/v2.3.4.rst
.. include:: previous_versions/v2.3.3.rst
.. include:: previous_versions/v2.3.2.rst
.. include:: previous_versions/v2.3.1.rst
.. include:: previous_versions/v2.3.0.rst
.. include:: previous_versions/v2.2.1.rst
.. include:: previous_versions/v2.2.0.rst
.. include:: previous_versions/v2.1.2.rst
.. include:: previous_versions/v2.1.1.rst
.. include:: previous_versions/v2.1.0.rst
.. include:: previous_versions/v2.0.3.rst
.. include:: previous_versions/v2.0.2.rst
.. include:: previous_versions/v2.0.1.rst
.. include:: previous_versions/v2.0.0.rst
.. include:: previous_versions/v1.10.1.rst
.. include:: previous_versions/v1.10.0.rst
.. include:: previous_versions/v1.9.5.rst
.. include:: previous_versions/v1.9.4.rst
.. include:: previous_versions/v1.9.3.rst
.. include:: previous_versions/v1.9.2.rst
.. include:: previous_versions/v1.9.1.rst
.. include:: previous_versions/v1.9.0.rst
.. include:: previous_versions/v1.8.5.rst
.. include:: previous_versions/v1.8.4.rst
.. include:: previous_versions/v1.8.3.rst
.. include:: previous_versions/v1.8.2.rst
.. include:: previous_versions/v1.8.1.rst
.. include:: previous_versions/v1.8.0.rst
.. include:: previous_versions/v1.7.3.rst
.. include:: previous_versions/v1.7.2.rst
.. include:: previous_versions/v1.7.1.rst
.. include:: previous_versions/v1.7.0.rst
.. include:: previous_versions/v1.6.0.rst
.. include:: previous_versions/v1.5.0.rst
.. include:: previous_versions/v1.4.0.rst
.. include:: previous_versions/v1.3.1.rst
.. include:: previous_versions/v1.3.0.rst
.. include:: previous_versions/v1.2.0.rst
