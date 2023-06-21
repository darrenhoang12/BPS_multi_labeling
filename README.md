# Multi-labeling the particle type and damage intensity of mice nuclei
Creating a machine learning model that would be able to predict multi-labels of particle type and the intensity of irradiation on mice nuclei.

## How to use?
We included two models that required training: <br />
* `mlp_model.py` (baseline) - Uses the MLPClassifier from sklearn.
* `lenet_scratch.py` (CNN deep-learning) - Uses a Lenet-5 CNN model built on PyTorch.

Installing dependencies:
* yaml files are in `environments/setup/*.yml`

Training the models:
* Make sure to uncomment `bps_datamodule.prepare_data()` in lenet_scratch.py to download the training image-data. The process uses boto3 and PyTorch to gather image data from AWS and transform it into ML-ready data.
* `python src/models/mlp_model.py`
* `python src/models/lenet_scratch.py`

Run `lenet_scratch.py` first to download image data.

## Overarching problem
Astronaut health - Astronauts' exposure to ionizing radiation can cause: <br />
* DNA damage
* Central nervous system effects
* Immune system effects <br />

The longer astronauts stay in space, the more likely these problems are to arise. However, it is difficult to study this problem. To be able to study and understand spaceflight-induced biological changes, we need subjects to experiment on. Conducting experiments on humans is certainly out of the question, due to a large discussion of ethical issues and risks. So how might we solve this problem?

## HOW MIGHT WE use Machine Learning to predict the particle type and amount of damage based on images of DNA damaged mice cells?
As biologically similar organisms, we can conduct experiments on mice for the benefit of humankind. This is where our dataset comes in. Our BPS Microscopy Dataset contains images of nuclei from mouse cells that are irradiated with iron or X-ray particles, and displays a marker for DNA damage. <br />
<br />
Utilizing machine learning, we want to understand the health effects of radiation exposure on astronauts to potentially discover optimal recovery paths for individuals exposed to radiation particles during space travel. We will do this through the predictions of multi-labels, specifically `<particle, dosage>`. Being able to predict multi-labels of this model will grant us valuable insights into radiation damage and patterns of between nuclei images and damage/particle types.

## Collaborators:
Darren Hoang (Student) <br />
Jake Leue (Student) <br />
Diya Mirji (Student) <br />
Thien Vu (Student) <br />
Nadia Ahmed (Professor) <br />
Dr. Lauren Sanders (NASA GeneLab Scientist) <br />

##
