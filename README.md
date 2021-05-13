<p align="center">
    <img src="https://raw.githubusercontent.com/activeloopai/Hub/master/docs/logo/hub_logo.png" width="50%"/>
    </br>
    <h2 align="center">Dataset management for deep learning applications
 </h2>
<p align="center">
    <a href="http://docs.activeloop.ai/">
        <img alt="Docs" src="https://readthedocs.org/projects/hubdb/badge/?version=latest">
    </a>
    <a href="https://pypi.org/project/hub/"><img src="https://badge.fury.io/py/hub.svg" alt="PyPI version" height="18"></a>
    <a href="https://pepy.tech/project/hub"><img src="https://static.pepy.tech/personalized-badge/hub?period=month&units=international_system&left_color=grey&right_color=orange&left_text=Downloads" alt="PyPI version" height="18"></a>
    <a href="https://app.circleci.com/pipelines/github/activeloopai/Hub">
    <img alt="CircleCI" src="https://img.shields.io/circleci/build/github/activeloopai/Hub?logo=circleci"> </a>
     <a href="https://github.com/activeloopai/Hub/issues">
    <img alt="GitHub issues" src="https://img.shields.io/github/issues/activeloopai/Hub"> </a>
    <a href="https://codecov.io/gh/activeloopai/Hub/branch/master"><img src="https://codecov.io/gh/activeloopai/Hub/branch/master/graph/badge.svg" alt="codecov" height="18"></a>
  <h3 align="center">
   <a href="https://docs.activeloop.ai/en/latest/?utm_source=github&utm_medium=readme&utm_campaign=button"><b>Documentation</b></a> &bull;
   <a href="https://docs.activeloop.ai/en/latest/?utm_source=github&utm_medium=readme&utm_campaign=button"><b>Getting Started</b></a> &bull;
   <a href="https://docs.activeloop.ai/en/latest/?utm_source=github&utm_medium=readme&utm_campaign=button"><b>Tutorials</b></a> &bull;
  <a href="https://join.slack.com/t/hubdb/shared_invite/zt-ivhsj8sz-GWv9c5FLBDVw8vn~sxRKqQ"><b>Slack Community</b></a> &bull;
  <a href="https://twitter.com/intent/tweet?text=The%20fastest%20way%20to%20access%20and%20manage%20PyTorch%20and%20Tensorflow%20datasets%20is%20open-source&url=https://activeloop.ai/&via=activeloopai&hashtags=opensource,pytorch,tensorflow,data,datascience,datapipelines,activeloop,dockerhubfordatasets"><b>Twitter</b></a>
 </h3>

## Why use Hub?
**Data scientists spend the majority of their time building infrastructure, transferring data, and writing boilerplate code. Hub streamlines these tasks so that users can focus on building amazing ML models.**

Hub enables users to stream unlimited amounts of data from the cloud to any machine without sacrificing performance compared to local storage. In addition, Hub connects datasets to pytorch and tensorflow with minimal boilerplate code, and it contains powerful tools for version control, building ML pipelines, and running distributed workloads.

Hub is best suited for images, videos, or text, and it works locally or on any cloud.

Google, Waymo, Red Cross, Omdena, and Rarebase use Hub.

## Benchmarks
COMING SOON


## Features 
### Current Release

* Easy creation of datasets and hosting on Activeloop Cloud or S3
* Rapid dataset streaming to any machine.
* Simple dataset integration to pytorch with no boilerplate code
* Dataset query using custom filter functions without having to download the entire dataset
* Rapid data processing using transforms on distributed compute
* Linear data pipelines
* Rapid [visualization](http://app.activeloop.ai/?utm_source=github&utm_medium=repo&utm_campaign=readme) of image datasets via integration with Managed Hub
 <p align="center">
    <br>
    <img src="https://raw.githubusercontent.com/activeloopai/Hub/master/docs/visualizer%20gif.gif" width="75%"/>
    </br>
NEED TO UPDATE: Visualization of a dataset uploaded to Hub via app.activeloop.ai (free tool).
</p>

### Coming Soon

* Datasets hosting on Google Cloud and Azure
* Datasets integration to tensorflow
* Version control
* Dataset query using text-based query language
* Loading of data in random order without having to download the entire dataset
* DAG and continuous pipelines

## How does Hub work?

Hub stores datasets as chunked compressed arrays, which significantly increases data transfer speeds between network-connected machines. This eliminates the need to download entire datasets before running code, because computations and data streaming can occur simultaneously without meaningfully increasing the total runtime.

Hub also significantly reduces the time to build ML workflows, because its API eliminates boilerplate code that is typically required for data wrangling.

## Getting Started
Hub is written in 100% python and can be quickly installed using pip.
```sh
pip3 install hub
```
Accessing datasets in Hub requires a single line of code. Run this snippet to get the first thousand images in the [MNIST database](https://app.activeloop.ai/dataset/activeloop/mnist/?utm_source=github&utm_medium=repo&utm_campaign=readme) in the numpy array format:
```python
from hub import Dataset

mnist = Dataset("activeloop/mnist")
mnist_np = mnist["image"][0:1000].compute()
```
To access and train a classifier on your own Hub dataset stored in cloud, run:
```python
my_dataset = Dataset("http://s3.amazonaws.com/[my_bucket_name]/")
my_dataset_pytorch = my_dataset.to_pytorch(lambda x: (x["image"], x["label"]))

train_loader = torch.utils.data.DataLoader(my_dataset_pytorch, batch_size=1, num_workers=0)

## Training Loop Here ##
```

## Documentation
Getting started guides, examples, tutorials, API reference, and other usage information can be found on our [documentation page](http://docs.activeloop.ai/?utm_source=github&utm_medium=repo&utm_campaign=readme). 

## For Students and Educators
Hub users can access and visualize a variety of popular datasets through a free integration with Activeloop's Managed Hub. Users can also create and store their own datasets and make them available to the public. Free storege up to ZZ GB is available.

## Community

Join our [**Slack community**](https://join.slack.com/t/hubdb/shared_invite/zt-ivhsj8sz-GWv9c5FLBDVw8vn~sxRKqQ) to learn more about dataset management using Hub and to get help from the Activeloop team and other users.

We'd love your feedback by completing our 3-minute [**survey**](https://forms.gle/rLi4w33dow6CSMcm9).

As always, thanks to our amazing contributors!    

<a href="https://github.com/activeloopai/hub/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=activeloopai/hub" />
</a>

Made with [contributors-img](https://contrib.rocks).

Please read [CONTRIBUTING.md](CONTRIBUTING.md) to get started with making contributions to Hub.


## README Badge

Using Hub? Add a README badge to let everyone know: 


[![hub](https://img.shields.io/badge/powered%20by-hub%20-ff5a1f.svg)](https://github.com/activeloopai/Hub)

```
[![hub](https://img.shields.io/badge/powered%20by-hub%20-ff5a1f.svg)](https://github.com/activeloopai/Hub)
```



## Disclaimers

### Dataset Licenses
Hub users may have access to a variety of publicly available datasets. We do not host or distribute these datasets, vouch for their quality or fairness, or claim that you have license to use the datasets. It is your responsibility to determine whether you have permission to use the datasets under their license.

If you're a dataset owner and do not want your dataset to be included in this library, please get in touch through a [GitHub issue](https://github.com/activeloopai/Hub/issues/new). Thank you for your contribution to the ML community!

### Usage Tracking
By default, we collect anonymous usage data using Bugout (here's the [code](https://github.com/activeloopai/Hub/blob/853456a314b4fb5623c936c825601097b0685119/hub/__init__.py#L24) that does it). It does not collect user data and it only logs the Hub library's own actions. This helps our team understand how the tool is used and how to build features that matter to you! You can easily opt-out of usage tracking during login.

## Acknowledgment
This technology was inspired by our research work at Princeton University. We would like to thank William Silversmith @SeungLab for his awesome [cloud-volume](https://github.com/seung-lab/cloud-volume) tool. We are heavy users of [Zarr](https://zarr.readthedocs.io/en/stable/) and would like to thank their community for building such a great fundamental block. 
