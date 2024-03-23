# Scalable Cloud-Based Distributed Computing for Efficient Big Data Analytics: A Dask Integration Approach

In this project, we are building a platform designed to be dynamically scalable based on user demand. At its core, it is the integration of Dask, a parallel execution framework, with JupyterHub, containerized and deployed on a cloud instance. We intend to benchmark the performance of Dask as a distributed computing framework on our cluster by conducting computationally intensive hyperparameter tuning of tree-based XGBoost algorithm on big data. Through systematic variations in input format, chunk size, task schedulers, worker nodes, clusters, and threading configurations, we seek to quantify the performance and compare it to baseline values obtained from running the program on the instance without distributing the workload. Our evaluation benchmarking serves two purposes: 1) to compare the performance of running computationally intensive ML algorithms with and without parallelizing the workload with Dask on cloud. 2) To understand in depth the many components of distributed computing that impact its performance.

## **Setup**

We intend to make use of a cloud service for the project either AWS or Jetstream. But before we deploy it on either of the services we intend to first develop and test on our local machines. How we plan on achieving this is by using a tool called minikube that helps setup a local kubernetes cluster with a configuration choice of our own. The next step after this would be to install the dask gateway and jupyterhub. Post that we can containerize the work done in JupyterHub, which can then be directly deployed on cloud without any need to worry about dependencies or installations that would increase our time spent on the cloud services thereby increasing the cost of using the cloud service. Below is a visualization of the what the whole setup looks like:



![Visualization_of_the_system](https://github.com/subhadramishra1994/ECC_Project_2024/assets/25883716/cc7100a2-31d6-4dfb-9a6e-2d7c68c8873f)

More details on the setup can be found [here](https://docs.google.com/document/d/1ahqIBX79Bf210f6q3yIH15cdMsiceaekGw57_SRHdCc/edit?usp=sharing)
## **Integration of Dask**

We aim to integrate Dask and XGBoost for hyperparameter optimization and regression tasks. Initially, we set up a local Dask cluster to utilize distributed computing capabilities. Synthetic data was generated and transformed into Dask arrays for compatibility with Dask's distributed computing framework. We split the data into training and testing sets using Dask's data-splitting functionality. To optimize hyperparameters, we defined an objective function utilizing Dask's distributed computing features for model training and prediction. Optuna facilitated hyperparameter optimization, with a study object created to minimize the objective function. Our experimentation resulted in the identification of optimal hyperparameters and their corresponding root mean square error (RMSE) value. Finally, we closed the Dask client and cluster to release computational resources, ensuring efficient parallelization and distributed computing throughout the project for handling extensive datasets and optimizing computational performance.

