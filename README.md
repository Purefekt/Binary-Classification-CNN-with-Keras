# Custom CNN with Keras

## Installing with Conda
This project uses Keras with PlaidML to train and uses TensorFlow to test the model. If we install both TensorFlow and PlaidML on the same virtual environment then TensorFlow will take precedence over PlaidML and we wont be able to use an AMD GPU since it will default to CPU. This is why we should create two different virtual environments:
- veers_custom_cnn_env -> will be used for notebooks 1, 2 and 3
- testing_model_env -> will be used for notebook 2
This also means you will have to add both kernels to jupyter notebook kernels. The steps to do all this are mentioned below.

Clone this project and cd into your project directory.  

Run this command to automatically create the conda environment called 'veers_custom_cnn_env' and install all packages
```
conda env create -f environment_1.yml
```
Activate this virtual environment
```
conda activate veers_custom_cnn_env
```
Add this kernel to jupyter notebook kernels
```
python -m ipykernel install --user --name='veers_custom_cnn_env'
```
Now this kernel will appear on jupyter notebook. Deactivate this environment.
```
conda deactivate
```
Now install the second environment
```
conda env create -f environment_2.yml
```
Activate this virtual environment
```
conda activate testing_model_env
```
Add this kernel to jupyter notebook kernels
```
python -m ipykernel install --user --name='testing_model_env'
```
Deactivate this environment
```
conda deactivate
```
If you run this command, you will see that we have created both environments
```
conda env list
```

## Running the Project
Activate the first environment
```
conda activate veers_custom_cnn_env
```
Set PlaidML as backend
```
plaidml-setup
```
```
Enable experimental device support? (y,n)[n]:n
```
On most devices 1 would be your CPU, 2 would be the integrated GPU on your CPU and 3 would be your dedicated GPU. Choose 3.
```
Please choose a default device: 3
```
```
Save settings to /Users/veersingh/.plaidml? (y,n)[y]:y
```
Cd into the project directory

Start the jupyter notebook server
```
jupyter notebook
```
Now you can run the notebooks 1,2 and 3. Make sure to set the kernel to 'veers_custom_cnn_env'

Deactivate this environment
```
conda deactivate
```
Activate the second environment
```
conda activate testing_model_env
```
Cd into the project directory

Start the jupyter notebook server
```
jupyter notebook
```
Now you can run the notebook 4. Make sure to set the kernel to 'testing_model_env'