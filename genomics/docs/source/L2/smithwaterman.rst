=========================================
Xilinx Smithwaterman Genomics
=========================================

Smithwaterman demo resides in ``L2/demos/smithwaterman`` directory.

Xilinx Smithwaterman Algorithm is FPGA based implementation of
standard Smithwaterman. Xilinx implementation of Smithwaterman application                                                                                   is aimed for achieving high throughput. This
Xilinx Smithwaterman application is developed and tested on Xilinx Alveo U200. 


Results
-------

Resource Utilization 
~~~~~~~~~~~~~~~~~~~~~

Table below presents resource utilization of Xilinx Smithwaterman Genomics
kernels. The final Fmax achieved is 300MHz 

============= ====== ====== ====== ======  ==== 
Flow           LUT   LUTMem  REG    BRAM   URAM 
============= ====== ====== ====== ======  ==== 
Smithwaterman  150K   16k    212K   0.3k    0       
============= ====== ====== =====  ======  ==== 

Performance Data
~~~~~~~~~~~~~~~~

Table below presents kernel throughput achieved for a single compute
unit. 

====================== =========================
Topic                      Results
====================== =========================
Genomics Throughput        267GCUPS 
====================== =========================

Note: Overall throughput can still be increased with multiple compute
units.

Software & Hardware
-------------------

::

     Software: Xilinx Vitis 2021.2
     Hardware: xilinx_u200_xdma_201830_2 (Xilinx Alveo U200)

Executable Usage
----------------
 
1. To execute single file for genomics  : ``./build/xil_sw -xbin ./build/xclbin_<xsa_name>_<TARGET mode>/<krnl_smithwaterman.xclbin> -c <file_name>``
2. To validate single file (genomics)   : ``./build/xil_sw -xbin ./build/xclbin_<xsa_name>_<TARGET mode>/<krnl_smithwaterman.xclbin> -t <file_name>``
 
           
      - ``<files.list>``: Contains various file names with current path

      - Note: Default arguments are set in Makefile

The usage of the generated executable is as follows:

.. code-block:: bash

   Usage: application.exe -[-h-t-l-xbin-B-id]
          --help,                -h        Print Help Options
          --test,                -t        Xilinx genomics
          --test_list,           -l        Xilinx genomics on Input Files
          --max_cr,              -mcr      Maximum CR                                             
          --xclbin,              -xbin     XCLBIN
          --device_id,           -id       Device ID                                             Default: [0]
        
