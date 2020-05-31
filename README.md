#### The goal of this project is to develop a tool that will automatically identify a structure (called basal body) from images and estimate its orientation.

This readme present quickly the goal of the project from IT point of view. For more information about the scientific part, see the (incoming) documentation and these 2 papers:
Vu et al. 2019: https://pubmed.ncbi.nlm.nih.gov/31743666/
Basquin et al. 2019: https://pubmed.ncbi.nlm.nih.gov/31743665/

Basically two mains step will be require:  
- Detection of the structures
- Orientation of the structures

**For the Artificial Neural Network project in DSTI, I will focus on the second part:  
Develop a tool that will estimate the orientation of the structure, thanks to a Convolution Neural Network.**


## Introduction  
Schmidtea mediterranea is a flat worm (planarian) which glide on substrate thanks to the coordinated beating of thousands of structure, called cilia, that decorate his ventral epidermis. The length of this animal range from ~200µm to 3cm with a 1:3 ratio (width:length). The cilia is anchored to the worm through a structure called basal body. On each basal body 2 main structures located in opposition (the rootlet and the basal foot (BB)) are required to orient the beating of the cilia. With a density of ~1 BB/µm², the smaller worms are decorated with a least 15000  BBs. So far, to study the orientation of the BBs, two strategies has been adopted. The first one was to use a tool that detect and orient BBs automatically (Vu et al. 2019). The second one (that I led), was a manual annotation a thousands of basal bodies to get there orientation (Basquin et al. 2019). The first method give a good idea of the orientation of the structures at the scale of the animal, but due to the not so good quality of the orientation, a lot of information are lost locally. In opposition, the second method is very precise but heavily time consuming.

As I already annotate more than 500 000 basal bodies, the idea of this project is to feed a Convolution Neural Network with the annotated images to get the orientation of the BBs with a great accuracy. If I succeed the next steps will to develop a tool to detect automatically the basal bodies on a image.


## On the use of CNN to detect orientation basal bodies
I split my code into 3 parts:  
- Extraction of annotated structure.
- Training of the CNN.
- Validation of the model

### Extraction of annotated BBs.
My previous work led me to annotate thousand of BBs. Those annotations were stored in dozens of excel files 
