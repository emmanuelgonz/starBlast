|CyVerse logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

starBlast
=========

.. contents::

What is starBlast?
------------------

starBlast blasts stars and starts blasting stars

starBlast VICE
~~~~~~~~~~~~~~

VICE is a Visual and Interactive Computing Environment which is the latest feature in CyVerse’s Discovery Environment (DE) for running interactive apps such as Rstudio and Jupyter Notebooks. 


starBlast Atmosphere Cloud
~~~~~~~~~~~~~~~~~~~~~~~~~~

atmosphere starBlast breathes life into stars

starBlast HPC
~~~~~~~~~~~~~

High performance computers blast starblast blast queries with performance that is high in the stars


What is sequenceServer?
-----------------------

sequenceServer sequences all servers and serves a sequencing service.

What is Work_Queue?
-------------------

Workqueue queues work to workers which are queued in a work queue.


Platform(s)
-----------

*We will use the following CyVerse platform(s):*

.. list-table::
    :header-rows: 1

    * - Solution
      - Platform
      - Capacity
      - Link
      - Platform Documentation
      - Learning Center Docs
    * - starBlast VICE
      - Discovery Environment
      - 5-15 Students
      - `Discovery Environment <https://de.cyverse.org/de/>`_
      - `DE Manual <https://wiki.cyverse.org/wiki/display/DEmanual/Table+of+Contents>`_
      - `Guide <https://learning.cyverse.org/projects/discovery-environment-guide/en/latest/>`__
    * - starBlast Atmosphere
      - Atmosphere Cloud / Docker
      - 25-50 Students
      - `Atmosphere <https://atmo.cyverse.org/de/>`_
      - `Atmosphere Manual <https://wiki.cyverse.org/wiki/display/DEmanual/Table+of+Contents>`_
      - `Guide <https://learning.cyverse.org/projects/discovery-environment-guide/en/latest/>`__
    * - starBlast HPC
      - HPC & Atmosphere Cloud
      - 50-100 Students
      - `cctools <https://atmo.cyverse.org/de/>`_
      - `PBS on HPC  <https://wiki.cyverse.org/wiki/display/DEmanual/Table+of+Contents>`_
      - `Workqueue <https://learning.cyverse.org/projects/discovery-environment-guide/en/latest/>`__

----

VICE Setup
----------
To set up a custom database on the VICE platform, ...

1. Click on the following button to quick launch sequence server with two blast databases (Human_GRCh38_p12 & Mouse_GRCm38_p4)

	|sequenceServer|_
	
2. Click [Launch Analysis]
3. Check the Bell Icon for a link to your sequenceserver instance
4. Start BLASTING

----

Atmosphere Cloud Setup
----------------------
To deploy slastEasy setup on CyVerse Atmosphere cloud, you will need access to `Atmosphere <https://atmo.cyverse.org/de/>`_.

You will need to launch a Master Atmosphere instance that will host sequenceServer and one or more Worker Atmosphere instances as needed to distribute the blast jobs. 

Both the Master and Worker Virtual Machine instances use Docker containers to run sequenceserver and connect Workers. 

Setting Up Master Instance
~~~~~~~~~~~~~~~~~~~~~~~~~~
1. Go to https://atmo.cyverse.org and log in with your Cyverse Username and Password
2. Launch a Master (medium1) instance which will broadcast as a Master using `this <https://atmo.cyverse.org/application/images>`_ image with docker preinstalled.
3. When the instance is ready showing Active (with a green dot) ssh into your virtual machine using ssh <CYVERSE_USERNAME>@<MASTER_VM_IP_ADDRESS> and enter your cyverse password.

4. copy and pase the following code to launch sequence server ready to distribute BLAST queries to workers

.. code:: 

   docker blah blah blah

Setting Up Worker Instance
~~~~~~~~~~~~~~~~~~~~~~~~~~
1. Go to https://atmo.cyverse.org and log in with your Cyverse Username and Password
2. Launch a Worker (XLarge1) instance which will connect to the Master using `this <https://atmo.cyverse.org/application/images>`_ image with docker preinstalled.
3. When the instance is ready showing Active (with a green dot) ssh into your virtual machine using ssh <CYVERSE_USERNAME>@<WORKER_VM_IP_ADDRESS> and enter your cyverse password.

4. copy and pase the following code to connect the Worker to the Master. You will need to copy the Master's IP Address and replace <WORKER_VM_IP_ADDRESS> with the actual IP Address of the MASTER. This will tell the Worker where to find the master. 

.. code:: 

   docker blah <MASTER_VM_IP_ADDRESS> blah 
   
Start Blasting
~~~~~~~~~~~~~~

Enter the <MASTER_VM_IP_ADDRESS> in your browser using the actual Master IP address to start BLASTING!

.. code::

   <WORKER_VM_IP_ADDRESS>

----

HPC Setup
---------

First, you will need to follow the above steps for setting up a Worker instance on Atmosphere. Then you can follow these steps to set up Workers on HPC using PBS scripts:

For more info on setting up PBS scripts andusing qsub see <add link here>

Once you have a Master Atmosphere Instance: 
1. Log in to hpc
2. create PBS script <add instructions to pbs>
	- load/get cctools 
	- worqueue_factory <MASTER_VM_IP+ADDRESS>
3. Use the qsub command to run PBS scripts

.. code::
    
   qsub blah blah blah blah
   
4. Start BLASTING! Enter the <MASTER_VM_IP_ADDRESS> in your browser using the actual Master IP address.

.. code::

   <WORKER_VM_IP_ADDRESS>
   
----


----

**Fix or improve this documentation**

- On Github: `Repo link <https://github.com/sateeshperi/starBlast/>`_
- Send feedback: `Tutorials@CyVerse.org <Tutorials@CyVerse.org>`_

----

|Home_Icon|_
`Learning Center Home`_

.. |sequenceServer| image:: https://de.cyverse.org/Powered-By-CyVerse-blue.svg
.. _sequenceServer: https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=0ade6455-4876-49cc-9b37-a29129d9558a&app-id=ab404686-ff20-11e9-a09c-008cfa5ae621

.. |RMTA-deseq2| image:: https://de.cyverse.org/Powered-By-CyVerse-blue.svg
.. _RMTA-deseq2: https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=1444198d-068f-4cf1-a3d1-df30e6d678f2&app-id=58f9a86c-2a74-11e9-b289-008cfa5ae621

.. |RMTA_quick_launch_1| image:: ./img/RMTA_quick_launch_1.png
    :width: 450
    :height: 200
.. _RMTA_quick_launch_1: http://learning.cyverse.org/
.. |RMTA_quick_launch_3| image:: ./img/RMTA_quick_launch_3.png
    :width: 450
    :height: 200
.. _RMTA_quick_launch_3: http://learning.cyverse.org/

.. |DESeq2_quick_launch_1| image:: ./img/DESeq2_quick_launch_1.png
    :width: 450
    :height: 200
.. _DESeq2_quick_launch_1: http://learning.cyverse.org/
.. |DESeq2_quick_launch_3| image:: ./img/DESeq2_quick_launch_3.png
    :width: 450
    :height: 200
.. _DESeq2_quick_launch_3: http://learning.cyverse.org/

.. |RNAseq_Webinar_test_data| image:: ./img/RNAseq_Webinar_test_data.png
    :width: 500
    :height: 250
.. _RNAseq_Webinar_test_data: http://learning.cyverse.org/

.. |CyVerse logo| image:: ./img/cyverse_rgb.png
    :width: 500
    :height: 100
.. _CyVerse logo: http://learning.cyverse.org/
.. |Home_Icon| image:: ./img/homeicon.png
    :width: 25
    :height: 25
.. _Home_Icon: http://learning.cyverse.org/
.. |discovery_enviornment| raw:: html

    <a href="https://de.cyverse.org/de/" target="_blank">Discovery Environment</a>
