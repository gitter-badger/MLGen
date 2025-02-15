# MLGen
MlGen is a tool which helps you to generate machine learning code with ease.
MLGen uses a ".mlm" file format which is a file with YML like syntax.
This tool as of now supports keras and tensorflow2.0(not fully supported)

`pip install mlgen`

## CLI commands--->
To init files  
`mlgen -i | --init <file name>`   
To generate a specific template (optional)  
`mlgen -g | --gen <neural network type> --backend | -be <lib to use> -t jupyter`  
To generate the ml python file  
`mlgen -r . `

## MLM file syntax --->

**file**: name of the python file to be created

**version**: version of python being used

**backend**: which machine learning platform if to be used

**gpu**: (bool) is gpu being used or not

**data**: location of the dataset can be a URL/ folder location on machine

**split**:(int) slipt in training and testing data. automatically converted to a decimal

**coloumns_feature**: list of coloumns being used for the prediction

**nill_data**: basic null data handling in non categorical datatypes. Available techiniques remove, mean, mode, median 

**nill_data_categorical**: basic null data handling for categorical datatypes. Available techiniques remove, max, min


**NeuralNetwork_type**: the type of neural network being used such as ANN, CNN, LSTM
<pre>
layer1:  
    number_neurons: (int) number of neurons  
    input_dim: input dimensions of the first layer  input 
    activation: activation function being used 
    dropout: (optional)  
       dropout: (int) dropout percentage  
       noise_shape: (int) noise shape (optional)  
       seed: (int) seed value (optional)  
layer2:  
    number_neurons: (int) number of neurons  
    activation: activation function being used  
    dropout: (optional)  
        dropout: (int) dropout percentage  
        noise_shape: (int) noise shape (optional)  
        seed: (int) seed value (optional)  


compile:  
    epochs: (int) number of epoch  
    batch_size: (int) batch size  
    verbose: (int) verbose value 0,1,2  
    optimizer:  optimizer being used  
    loss: loss type  
    metrics: (array)  
        - metrics type  


checkpoint: (optional)  
    monitor: metrix type  
    verbose: (int) batch size  
    save_best_only: (bool)  
    mode: mode such as min max  


save_model: (optional)  
    file: file name to save model in  
    save: save type. Available options weights and model
</pre>