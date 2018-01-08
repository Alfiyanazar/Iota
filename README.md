

   # IOTA 
    
   ## Step by step guide on how to run an IOTA node on windows.

   A guide to: 
-	Setup all requirements for an IRI. 
-	Download the latest release of II. 
-	Or build the IRI code to an executable release.
-	Run IRI. 
   
# Finding neighbours 
You can find neighbors in the #nodesharing Slack channel [ http://slack.iota.org/  ]. If you want to get tokens for your testcase, please just ask in one of the communication channels as well.
 
Within the GUI, select ‘Tools -> Edit Neighbours’ to add neighbours.  
 
# Steps in setting up Iota 
 
 # Install IRI 
  
 You have two options, the preferred option is that you compile and get the .jar file yourself. The second option is that you utilize the provided jar, which is released regularly (when new updates occur) here:. 
  
  In order to install IRI, there are certain requirements to be considered. It should be noted that IRI only works on 64-bit system architectures. 
   
-	Java 8u66 or higher (Oracle) as shown in the image below.
-	On Windows, make sure that Microsoft Visual C++ 2015 Redistributable Update 3 is installed 

![alt text](https://github.com/Alfiyanazar/Iota/blob/master/pictures/java%20version.PNG)
  
Now, install the compiled version of IRI. You can find it in https://github.com/iotaledger/iri/releases. 
  
 # Compile IRI yourself 
Make sure to have Maven and Java 8 installed on your computer. 
  
 To compile & package 
 ```sh 
$ git clone https://github.com/iotaledger/iri 
$ cd iri 
$ mvn clean compile 
$ mvn package 
``` 
c

This will take some time. If the process is completed successfully you will see the result as “Build success”. 
  
  ![alt text](https://github.com/Alfiyanazar/Iota/blob/master/pictures/package.PNG)
  
 This will then create a target folder, in which you will find the compiled .jar (not the original one) which you can then use. 
  
 # Run IRI  
 # Locally 
 Running IRI is incredibly simple. 
 

```sh 

$ java -jar iri.jar -p 14600 
 
``` 
  
  ![alt text](https://github.com/Alfiyanazar/Iota/blob/master/pictures/iri.PNG)
  
This will start IRI at port 14600. In order to actually use IRI, you will need to find neighbours. It should be noted that IRI works with UDP and with TCP. As such, you can connect to your neighbours with either protocol. In order to get the most out of IRI, we have also made a set of flags available for you. 
 
Once you have successfully started IRI, it will create a database folder (either mainnetdb or testnetdb). 
 
 # Run IRI with .ini file 
 You can also provide an ini file to store all of your command line options and easily update 
(Especially neighbours) if needed. You can enable it via the -- config flag. Here is an example INI file: 
  
 ```sh 
[IRI] 
PORT = 14700 
UDP_RECEIVER_PORT = 14700 
NEIGHBORS = udp://my.favorite.com:15600 
IXI_DIR = ixi 
HEADLESS = true 
DEBUG = true 
TESTNET = true 
DB_PATH = db 
``` 
 
# Install GUI 
 
Go to the below link . 
 https://github.com/iotaledger/wallet/releases.  
 Download the respective version for your operating system. 
  
 # Install on windows 
 After you have downloaded the .exe file from our Github repo go to the Download folder and double click on the executable. After that you should see an installation screen, wait until it's finished. 
  
 Once the installation is completed, the app will automatically open as well as create Desktop shortcut. 
  
 Light vs. Full Node 
 The GUI wallet makes it possible to be used either as a lightwallet or as a full wallet. If used as a lightwallet, you are basically interacting either with your own hosted full node, or with the full node of a third party (often referred to as "light wallet provider"). 
  
 It should be noted that all sensitive functions (such as hashing and signing) happen client side. This means that if you interact with a light wallet provider, your seed or your private keys never leave your possession and the light wallet provider cannot steal your funds. However, when interacting with a third party, it should be noted that there are different security assumptions related to that, especially when making state-related API calls (such as getBalance and getInclusionStates). If your usage requires high security, make sure to use a quorum of lightwallet providers. 
  
-	Choose light wallet. 
-	Generate seed using seed generator and copy the seed to login to the wallet. 


![alt text](https://github.com/Alfiyanazar/Iota/blob/master/pictures/loginwallet.PNG)   
  
   
-	After you login, you'll see a menu with Balance, Send , Recieve and history. 

![alt text](https://github.com/Alfiyanazar/Iota/blob/master/pictures/wallet.PNG)   
-	Select recieve and attach to tangle. 

![alt text](https://github.com/Alfiyanazar/Iota/blob/master/pictures/attach.PNG)
 
  
In order to use Iri we have to connect to neighbours.  
 Get neighbours, therefore goto https://slack.iota.org/ and join the community and enter the channel nodesharing. On this cannel are more people like you searching for neighbours, just get in touch and find 4-9 Neighbours. 
Edit iri.ini suit your needs. 
 
IRI Testnet 
To make the development and the integration of IRI faster, we have setup a special testnet network where exchanges can test certain functionality without having to worry about losing tokens. Please join the #testnet channel on the IOTA Slack to be able to join this testnet network. You will have to launch your IRI instance with the --testnet flag. 
 
 
  ### For anyone interested in learning more about IOTA, you can check with the links given below:
https://iota.readme.io/reference#getnodeinfo
https://domschiener.gitbooks.io/iota-guide/content/core-and-libraries/iri.html

 
