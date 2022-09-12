# Kaggle as the platform for running Jupyter Notebooks

Kaggle is a cloud platform originally offering free services for machine learning. However it also allow user to create kernels that run Jupyter Notebooks.
We will look into how Kaggle can be used as the alternative platform (as opposed to Microsft's Azure or eResearch's NeCTAR Research Cloud platform) for
running Jupyter Notebooks. 

- [Register an account in Kaggle](#register-an-account-in-kaggle)
- [Create a notebook in Kaggle and upload input data files](#create-a-notebook-in-kaggle-and-upload-input-data-files)
- [Share notebook and data file](#share-notebook-and-data-file)
- [Account verification and adding packages to kernel](#account-verification-and-adding-packages-to-kernel)

<br/>

### Register an account in Kaggle

Go to https://www.kaggle.com/ and click on "Register". Then choose "Register with Google". Since the university mail system is integrated with google, you can
simply use your "upi@aucklanduni.ac.nz" to register.

![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/1-1.png) ![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/1-2.png)

You will then be redirected to a UoA page for authentication.  Once it's done, the next step is to make up your Username in Kaggle. By default, Kaggle will set your Username the same as your Display name. I highly recommend to manually change your Username" to the UPI (by clicking on the edit button). It will make it easier for other UoA members to locate you since Username is a unique identifier in Kaggle.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/1-3.png) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/1-4.png)

Once the registration is done, you can make more changes to your profile by clicking on your avatar icon on the top right of the page and then select "My Account". 

<br/>

### Create a notebook in Kaggle and upload input data files
After the registration you are ready to create your first notebok. Choose the "Notebooks" from the left panel then click on "New Notebook"
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/2-1.png)

Next you will be offered a few options to setup the kernel of the notebook.  If you want to create a Jupyter notebook, select "Python" as the language, and "Notebook" as the type. 
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/2-2.png)

Once the kernel is created, Kaggle will initialize the notebook with a few greeting messages and some example code. You can continue edit on the notebook or import
an existing notebook by selecting "File" then "Upload".  
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/2-3.png)

You can rename your notebook at any time by directly editing the title on the top left.  You can upload input data files by selecting  "File" then click on "Add or Upload data".
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/2-4.png)
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/2-5.png)

Once the input data files are uploaded, they will be stored in the folder "'/kaggle/input'", however the working directory by default is "/kaggle/working".  So when you access to the input file in the scripting environment, make sure to use the correct relative path. For example:
```sh
# Assume we uploaded a file called "graph1.txt", we can access it by using its relative path to the default working directory
g1=nx.read_edgelist("../input/graph1.txt")
```
Your notebook is automatically saved (stored in your Kaggle cloud) as "drafts" as you edit.  If you want to export the notebook to a local environment, select "File" then click "Download".
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/2-6.png)

<br/>

### Share notebook and data file
You can share your notebook with another person in Kaggle.  From your notebook click on the "Share" button on the top of the page, then select "Add collaborators".
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/3-1.png)
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/3-2.png)

In the next page, you can specify the collaborator that you want to share the notebook with. Simply search for the Username of that person, and from the drop down box that person should be the first on the list.  Since "Username" is an unique identifier in Kaggle, you can be sure that the person is the one you are looking for. You can share notebook with more than one person.
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/3-3.png)

By default, any input file you uploaded to your notebook is not visible to your collaborators. You will have to share it using a separate process. In your Kaggle home page, select "Data" from the left panel, then click on "YOUR DATASETS" and choose the the data that you want to share.  In the following window, select "settings" from the top panel and click on "Sharing" on the left, then search for the "Username" of the person you want to share data with.  
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/3-4.png)
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/3-5.png)

Once you shared the notebook and data file, your collaborator will be able to see them and make a copy of your notebook.
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/3-6.png)

<br/>

### Account verification and adding packages to kernel
By default you are not allowed to access the internet within the Kaggle container that runs your notebook.  To change that, you will need to verify your account with a mobile phone. Under your profile menu (top left corner) , select "My Account". Then scroll down a little bit and click on the link below "Phone Verification". Then follow the instructions to complete your phone verification. Beware that you can not reuse the same phone number from your previous verification, it will result in an account lock if you do that.
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/4-1.png)
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/4-2.png)

With your account verified, you will have the ability to add packages to your kernel using external repositories. From your notebook, turn "Internet" on.
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/4-3.png)

To install python packages, open a new cell in your notebook, and run the installation command.  In the example below, we try to use pip to install "ktransit", however it is missing the fortran compiler.
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/4-4.png)

To fix that we will use the “apt-get” command to install the fortran package for the kernel.
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/4-5.png)
![alt text](https://github.com/phu004/Kaggle_Instruction/blob/main/image/4-6.png)

Apart from internet access, account verification also give you access to more features in Kaggle such as using Kaggle's GPU node for acceleration.

