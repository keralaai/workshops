# Welcome to tensorflow study Jam: day 2 !


## Representation

**Feature engineering** means transforming raw data into a feature vector. 

Consider this dataset,

| Super hero     | PowerRange | Capabilities                     | Avengers cofounder|Snapified|
|----------------|------------|----------------------------------|-------------------|---------|        
| Iron man       | 95         | Flying, weapon making, tech.     |     Yes           |    No   |
| Dr. Strange    | 98         | Teleporting,weapon making, magic |     No            |    Yes  |
| Spiderman      | 94         | Webbing, spidersense,strength    |     No            |    Yes  |
| Captain America| 95         | Strength, fighting skills,fast   |     Yes           |    No   |  
| Black Panther  | 94         | Rich, fighting skills, tech,fast |     No            |    Yes  |
| Bruce Banner   | 50         | (in)ability to turn into hulk    |     Yes           |    No   |

Many machine learning models must represent the features as real-numbered vectors since the feature values must be multiplied by the model weights.


- **Integer and floating-point data** don't need a special encoding because they can be multiplied by a numeric weight.

- **Categorical values** have a discrete set of possible values. For example, there might be a feature called **Capabilities** with options that include:

[fast, fighting skills, flying, inability to turn into hulk, magic, Rich, Strength, Spidersense, tech, teleporting, webbing, weapon making]

One hot encoding for ironman : [0,0,1,0,0,1,0,0,1,0,0,1]


| Super hero     | PowerRange | Capabilities                     | Avengers cofounder|Snapified|
|----------------|------------|----------------------------------|-------------------|---------|        
| Iron man       | 95.0       | [0,0,1,0,0,1,0,0,1,0,0,1]        |     1             |   0     |
| Dr. Strange    | 98.0       | [0,0,0,0,1,0,0,0,0,1,0,1]        |     0             |   1     |
| Spiderman      | 94.0       | [0,0,0,0,0,0,1,1,0,0,1,0]        |     0             |   1     |
| Captain America| 95.0       | [1,1,0,0,0,0,1,0,0,0,1,0]        |     1             |   0     |
| Black Panther  | 94.0       | [1,0,1,0,0,1,0,0,1,0,0,0]        |     0             |   1     |
| Bruce Banner   | 50 .0      | [0,0,0,1,0,0,0,0,0,0,0,0]        |     1             |   0     |

In **Sparse representation** only nonzero values are stored. In sparse representations, an independent model weight is still learned for each feature value, as described above.
