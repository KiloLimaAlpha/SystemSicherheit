# SystemSicherheit
Repo for module system security in B-AI

Requirements for hardware execution:
  - 6th Generation Intel Core Processor or newer
  - Intel SGX option enabled in BIOS. 
    
Requirements for simulated execution:
  - Any Intel Core Processor
  
Operating System requirements:
  - Ubuntu 20.04 LTS 64-bit Desktop or Server version

To install the Intel SGX PSW, following tools are required: 
  
    $ sudo apt install libssl-dev libcurl4-openssl- dev libprotobuf-dev 

To install the Intel SGX SDK, following tools are required: 
  
    $ sudo apt install build-essential python-is-python3 

#Installation 

The current Linux installation packages (x64 only) are divided into three parts and needs to be installed in the fallowing order: 
  
    1. Intel SGX driver 
    2. Intel SGX platform software (PSW) 
    3. Intel SGX SDK. 

To install the driver, PSW and SDK you need root privileges.

To install the SGX driver without ECDSA attestation: 
  1. Download Intel SGX driver package from 
    
    https://download.01.org/intel-sgx/latest/linux-latest/distro/ubuntu20.04-server/
  
  2. Run the following command: 
    
    $ sudo ./sgx_linux_x64_driver.bin

To install the Intel SGX PSW (from the repository): 
  1. Add the repository to your sources. 
    
    $ echo 'deb [arch=amd64] https://- download.01.org/intel-sgx/sgx_repo/ubuntu focal main' | sudo tee /etc/apt/sources.list.d/intel-sgx.list 
    
  2. Add the key to trusted keys: 
    
    $ wget -qO - https://download.01.org/intel-sgx/sgx_ repo/ubuntu/intel-sgx-deb.key | sudo apt-key add - 
    
  3. Update apt and install the packages: 
    
    $ sudo apt update 

  launch service:
      
      $ sudo apt install libsgx-launch libsgx-urts 
      
  EPID-based attestation service:
      
      $ sudo apt install libsgx-epid libsgx-urts 

  algorithm agnostic attestation service:
      
      $ sudo apt install libsgx-quote-ex libsgx-urts 

To install the Intel SGX SDK 
  1. Download Intel SGX SDK package: sgx_linux_x64_sdk_<version>.bin from 
    
    https://download.01.org/intel-sgx/latest/linux-latest/distro/ubuntu20.04-server/
  
  2. Install the SDK using the following command: 
    
    $ ./sgx_linux_x64_sdk_<version>.bin 
  
  3. After the installation, the SGX SDK package is installed into the directory [User Input Path]/sgxsdk
    
  Run the command 
      
      $ source [User Input Path]/sgxsdk/environment 
      
  to set all environment variables. 
    
  4. Download the mitigation tools that are named as.ld.objdump.gold.r2.tar.gz from 
  
    https://download.01.org/intel-sgx/latest/linux-latest/
    
  unzip them and copy the tools to the directory of /usr/local/bin. 
  Make sure that these tools have execute permission. 



