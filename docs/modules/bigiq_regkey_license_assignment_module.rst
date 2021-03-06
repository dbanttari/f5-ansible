:source: bigiq_regkey_license_assignment.py

:orphan:

.. _bigiq_regkey_license_assignment_module:


bigiq_regkey_license_assignment - Manage regkey license assignment on BIG-IPs from a BIG-IQ
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.6

.. contents::
   :local:
   :depth: 2


Synopsis
--------
- Manages the assignment of regkey licenses on a BIG-IQ. Assignment means that the license is assigned to a BIG-IP, or, it needs to be assigned to a BIG-IP. Additionally, this module supported revoking the assignments from BIG-IP devices.




Parameters
----------

.. raw:: html

    <table  border=0 cellpadding=0 class="documentation-table">
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
                                                                                    <tr>
            <th colspan="2">Parameter</th>
            <th>Choices/<font color="blue">Defaults</font></th>
                        <th width="100%">Comments</th>
        </tr>
                    <tr>
                                                                <td colspan="2">
                    <b>device</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>When <code>managed</code> is <code>no</code>, specifies the address, or hostname, where the BIG-IQ can reach the remote device to register.</div>
                                                    <div>When <code>managed</code> is <code>yes</code>, specifies the managed device, or device UUID, that you want to register.</div>
                                                    <div>If <code>managed</code> is <code>yes</code>, it is very important that you do not have more than one device with the same name. BIG-IQ internally recognizes devices by their ID, and therefore, this module&#x27;s cannot guarantee that the correct device will be registered. The device returned is the device that will be used.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>device_password</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The password of the <code>device_username</code>.</div>
                                                    <div>When <code>managed</code> is <code>no</code>, this parameter is required.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>device_port</b>
                                                        </td>
                                <td>
                                                                                                                                                                    <b>Default:</b><br/><div style="color: blue">443</div>
                                    </td>
                                                                <td>
                                                                        <div>Specifies the port of the remote device to connect to.</div>
                                                    <div>If this parameter is not specified, the default of <code>443</code> will be used.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>device_username</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The username used to connect to the remote device.</div>
                                                    <div>This username should be one that has sufficient privileges on the remote device to do licensing. Usually this is the <code>Administrator</code> role.</div>
                                                    <div>When <code>managed</code> is <code>no</code>, this parameter is required.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>key</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The registration key that you want to assign from the pool.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>managed</b>
                                                        </td>
                                <td>
                                                                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li>yes</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Whether the specified device is a managed or un-managed device.</div>
                                                    <div>When <code>state</code> is <code>present</code>, this parameter is required.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>pool</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The registration key pool to use.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                                <td colspan="2">
                    <b>provider</b>
                                        <br/><div style="font-size: small; color: darkgreen">(added in 2.5)</div>                </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>A dict object containing connection details.</div>
                                                                                </td>
            </tr>
                                                            <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>password</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The password for the user account used to connect to the BIG-IP.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_PASSWORD</code>.</div>
                                                                                        <div style="font-size: small; color: darkgreen"><br/>aliases: pass, pwd</div>
                                    </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>server</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The BIG-IP host.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_SERVER</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>server_port</b>
                                                        </td>
                                <td>
                                                                                                                                                                    <b>Default:</b><br/><div style="color: blue">443</div>
                                    </td>
                                                                <td>
                                                                        <div>The BIG-IP server port.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_SERVER_PORT</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>user</b>
                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>The username to connect to the BIG-IP with. This user must have administrative privileges on the device.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_USER</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>validate_certs</b>
                                                        </td>
                                <td>
                                                                                                                                                                                                                    <ul><b>Choices:</b>
                                                                                                                                                                <li>no</li>
                                                                                                                                                                                                <li><div style="color: blue"><b>yes</b>&nbsp;&larr;</div></li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>If <code>no</code>, SSL certificates are not validated. Use this only on personally controlled sites using self-signed certificates.</div>
                                                    <div>You may omit this option by setting the environment variable <code>F5_VALIDATE_CERTS</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>timeout</b>
                                                        </td>
                                <td>
                                                                                                                                                                    <b>Default:</b><br/><div style="color: blue">10</div>
                                    </td>
                                                                <td>
                                                                        <div>Specifies the timeout in seconds for communicating with the network device for either connecting or sending commands.  If the timeout is exceeded before the operation is completed, the module will error.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>ssh_keyfile</b>
                                                        </td>
                                <td>
                                                                                                                                                            </td>
                                                                <td>
                                                                        <div>Specifies the SSH keyfile to use to authenticate the connection to the remote device.  This argument is only used for <em>cli</em> transports.</div>
                                                    <div>You may omit this option by setting the environment variable <code>ANSIBLE_NET_SSH_KEYFILE</code>.</div>
                                                                                </td>
            </tr>
                                <tr>
                                                    <td class="elbow-placeholder"></td>
                                                <td colspan="1">
                    <b>transport</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li>cli</li>
                                                                                                                                                                                                <li><div style="color: blue"><b>rest</b>&nbsp;&larr;</div></li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>Configures the transport connection to use when connecting to the remote device.</div>
                                                                                </td>
            </tr>
                    
                                                <tr>
                                                                <td colspan="2">
                    <b>state</b>
                                                        </td>
                                <td>
                                                                                                                            <ul><b>Choices:</b>
                                                                                                                                                                <li><div style="color: blue"><b>present</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                                <li>absent</li>
                                                                                    </ul>
                                                                            </td>
                                                                <td>
                                                                        <div>When <code>present</code>, ensures that the device is assigned the specified license.</div>
                                                    <div>When <code>absent</code>, ensures the license is revokes from the remote device and freed on the BIG-IQ.</div>
                                                                                </td>
            </tr>
                        </table>
    <br/>


Notes
-----

.. note::
    - For more information on using Ansible to manage F5 Networks devices see https://www.ansible.com/integrations/networks/f5.
    - Requires BIG-IP software version >= 12.
    - The F5 modules only manipulate the running configuration of the F5 product. To ensure that BIG-IP specific configuration persists to disk, be sure to include at least one task that uses the :ref:`bigip_config <bigip_config_module>` module to save the running configuration. Refer to the module's documentation for the correct usage of the module to save your running configuration.


Examples
--------

.. code-block:: yaml

    
    - name: Register an unmanaged device
      bigiq_regkey_license_assignment:
        pool: my-regkey-pool
        key: XXXX-XXXX-XXXX-XXXX-XXXX
        device: 1.1.1.1
        managed: no
        device_username: admin
        device_password: secret
        state: present
        provider:
          user: admin
          password: secret
          server: lb.mydomain.com
      delegate_to: localhost

    - name: Register a managed device, by name
      bigiq_regkey_license_assignment:
        pool: my-regkey-pool
        key: XXXX-XXXX-XXXX-XXXX-XXXX
        device: bigi1.foo.com
        managed: yes
        state: present
        provider:
          user: admin
          password: secret
          server: lb.mydomain.com
      delegate_to: localhost

    - name: Register a managed device, by UUID
      bigiq_regkey_license_assignment:
        pool: my-regkey-pool
        key: XXXX-XXXX-XXXX-XXXX-XXXX
        device: 7141a063-7cf8-423f-9829-9d40599fa3e0
        managed: yes
        state: present
        provider:
          user: admin
          password: secret
          server: lb.mydomain.com
      delegate_to: localhost





Status
------



This module is **preview** which means that it is not guaranteed to have a backwards compatible interface.




Author
~~~~~~

- Tim Rupp (@caphrim007)

