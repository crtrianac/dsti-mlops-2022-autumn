# Versioning

# Git refresher

## Why do we need version control?

![Version control issues](./assets/doc_ver_joke.png)

## Git basics

### What is Git?

- **Git**: Distributed Version Control System
- **Git repository**:
  - A directory of versioned files => saves the history of all changes
  - It exists as a local copy with “.git” at the root of the project
  - The user can decide which files to version (.gitignore file)
- **Providers**: GitHub, GitLab; self-managed

![Distributed Version Control System](./assets/distributed_vcs.png)

[Reference](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

### Data flow

![Git dataflow](./assets/git_dataflow.png)

### Git workflow

Typical branch organization:

![Git branching](./assets/git_branching.png)

[Reference](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

## Data versioning

![Logos DVC and Git](./assets/logo_dvc_git.png)

[DVC official site](https://dvc.org/)

### Roadmap

![Roadmap](./assets/roadmap.png)

### Problem definition

What do we need to track in Data Science project to be able to reproduce the results?

- **Dataset**:
  - Tabular
  - Images, video, sound, text
- **Code**:
  - Functionality, Hyper-parameters
  - Data pre-processing, Modeling
- **Results**:
  - Numeric (metrics)
  - Plots
- **Environment**:
  - Dependencies

### Data versioning use cases

Data beyond data science:

- **Data engineering** during data cleaning and dataset preparation
- Test data in **software engineering** to assure the functionality of the software
- Development and testing of **database applications**
- Ontology versioning for **Semantic Web**
- ...

### Data is in the heart of any ML project

Why is the exact version of a dataset important?

- Data quality management
- Reproducible training and re-training
- Automation of testing or deployment
- Use in applications and web services
- Audit

### Classical data versioning solutions and their downsides

Classical Software Engineering tools are not enough to solve ML reproducibility crisis.

- **Git**:
  - Not suitable for big files
  - Difficulties with binary files
- **Git-LFS**:
  - File size limitation (ex.: 2 GB for GitHub free account and 5 GB for GitHub Enterprise Cloud)
  - Data needs to be stored on servers of Git provider
- **External storage**:
  - Checksum calculation for any change in the dataset and placing them under version control
  - Consistency!!!

### What is DVC?

- Tracks **datasets** and **ML projects**
- Works with many types of **storages** (cloud, local, HDFS, HTTP…)
- Runs on top of a **Git repository**
- Supports building and running **pipelines**

We will focus on dataset tracking (versioning).

![How Git and DVC interact](./assets/interface_dvc_git.png)

### The exact version of the dataset can be extracted in through the API

![Which data version?](./assets/data_ver_joke.jpeg)

![Logos DVC and Python](./assets/logo_dvc_python.png)

- **DVC**:
  - Solves Git's limitation of the file sizes
  - Easy to learn (for Git users)
  - Contains Python API
- **Python**:
  - Widely used
  - Can access a specific version of a dataset directly through the DVC's Python API

### Practical example

![Example schema](./assets/lab_schema.png)


#DVC in practice
https://youtu.be/kLKBcPonMYw 
<img width="483" alt="image" src="https://github.com/crtrianac/dsti-mlops-2022-autumn/assets/36132629/4963b917-0576-424c-8671-0e4399ee9e93">

<img width="342" alt="image" src="https://github.com/crtrianac/dsti-mlops-2022-autumn/assets/36132629/d2644a22-3f44-44c2-bc4b-2d7dbda1ee9e">
Adding a DVC remote in google drive 
<img width="844" alt="image" src="https://github.com/crtrianac/dsti-mlops-2022-autumn/assets/36132629/b11ba901-f914-40bf-80ce-2b9675473ef4">
data is going going to be push ont hte file that you have created
now you can remove and add data via the git -> DVC-> cloud
<img width="365" alt="image" src="https://github.com/crtrianac/dsti-mlops-2022-autumn/assets/36132629/307b5ca2-a37b-4317-8537-d64f25b9f5b2">
lets cahnge the data set and move forward and backads 
copy and concatinate the data
dvc add-> adding it , commint it, pushing and then tracking it ( we now have 2 versions of our data storage
<img width="365" alt="image" src="https://github.com/crtrianac/dsti-mlops-2022-autumn/assets/36132629/4060de20-4918-4a48-a644-2dbf12d75301">
How can we move forward and backward
git add to track the changes on the repository you want to track
<img width="840" alt="image" src="https://github.com/crtrianac/dsti-mlops-2022-autumn/assets/36132629/ffc55cb2-0710-46df-8d50-d2d4cdc4eff0">
we can get the log
<img width="472" alt="image" src="https://github.com/crtrianac/dsti-mlops-2022-autumn/assets/36132629/56102b13-5eb2-4ca8-bd95-4e28c49f3e61">
