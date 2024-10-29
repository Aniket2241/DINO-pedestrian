#commands to run DINO

**NOTE**
This code utilizes Colab's features (like free GPUs), making it Colab-specific as paths for files were changed.If running on local machine just change the paths.

1. Git clone the original DINO repo : https://github.com/IDEA-Research/DINO.git
 
2. Install miniconda to work in a conda environment.Use following command :
   !wget -c https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
   !chmod +x Miniconda3-latest-Linux-x86_64.sh
   !bash ./Miniconda3-latest-Linux-x86_64.sh -b -f -p /usr/local
   
3.Install all dependencies.[!conda install -c pytorch pytorch torchvision
][!pip install -r /content/DINO/requirements.txt][!pip install torch torchvision timm gdown termcolor addict yapf pycocotools scipy]

4.Upload your dataset zip-file if working on platform like colab.

5.Unzip your file using python script :
import zipfile
import os
zip_file_path = '/content/Pedestrian_dataset_for_internship_assignment.zip'
extracted_folder = '/content/DINO/datasets'


with zipfile.ZipFile(zip_file_path, 'r') as zip_ref:
    zip_ref.extractall(extracted_folder)

os.listdir(extracted_folder)

6.Split your data into 160 train and 41 test and create annotation files for train and test at the same time using one script only that is mentioned in Dino.ipynb.

7.Download pretrained model checkpoint[Dino4 scale backbone resnet-50] using : !pip install gdown
!gdown --id 1eeAHgu-fzp28PGdIjeLe-pzGPMG2r2G_

8. Start training your model using : !bash /content/DINO/scripts/DINO_train.sh /content/DINO/datasets/Pedestrian_dataset_for_internship_assignment

0. Fine-tune model in config->DINO_4scale.py . For now imited access to high-performance GPUs restricted my ability to conduct extensive fine-tuning.

Link to my colab-file : https://github.com/Aniket2241/DINO-pedestrian/blob/main/Dino.ipynb



