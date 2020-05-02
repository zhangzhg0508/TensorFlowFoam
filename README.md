# TensorFlowFoam
A turbulence model built using a deep neural network trained in Tensorflow 1.15.

The following steps will get you started with a data-driven turbulence model deployed in OpenFOAM 5. I am assuming you have already installed and successfully run OpenFOAM 5 prior to this. Visit XX for more information on downloading and installing OpenFOAM 5. Also, this tutorial will be based on Linux (Ubuntu 18.04) at this point of time.

While training on the fly is also possible using this procedure - it would need some MPI magic to segregate resources for training and inference at the same time. That is an active topic of research - stay tuned. 

## Step 1: Download the Tensorflow C API

You can download the TensorFlow C API at `https://www.tensorflow.org/install/lang_c`. Follow instructions there to install on your machine. This tutorial/model is designed for the **Linux CPU only** release. Briefly, the instructions to install are:

1. `sudo tar -C /usr/local -xzf (downloaded file)`
2. `sudo ldconfig`

and you are good to go. If you want to install the API to an off-nominal location please consult the documentation at the previously mentioned link. 

## Step 2: Test that C API is running using Test_TF_C code

After Step 1 is complete test that your API is configured correctly by executing the following code (which you can save in `tf_hello_world.cpp`
```
//Working on some tensorflow and c++ implementations

#include <stdio.h>
#include <tensorflow/c/c_api.h>

int main() {
  printf("Hello from TensorFlow C library version %s\n", TF_Version());

  return 0;
}
```
by using 
```g++ hello_tf.cpp -ltensorflow```
and 
```./a.out```
to obtain the following output
```
Hello from TensorFlow C library version 1.15.0
```
If you have reached this point - congratulations you are ready to use TensorFlow *within* OpenFOAM 5. 

## Step 3: Train a model in the TensorFlow Python API

## Step 4: Export model to disk

## Step 5: Make modifications to standard OpenFOAM RANS (or LES) model case to call TensorFlow operations

## Step 6: Compile with wmake

## Step 7: Make changes to case 

## Step 8: Make changes to simpleFoam (if needed)

## Step 9: Deploy