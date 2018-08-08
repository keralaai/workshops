# Welcome to tensorflow study Jam: day 2 !


## Representation

**Feature engineering** means transforming raw data into a feature vector. 

Consider this dataset,

| Super hero     | PowerRange | Capabilities                     | Snapified|
|----------------|------------|----------------------------------|----------|        
| Iron man       | 95         | Flying, weapon making, tech.     |     No   |
| Dr. Strange    | 98         | Teleporting,weapon making, magic |     Yes  |
| Spiderman      | 94         | Webbing, spidersense,strength    |     Yes  |
| Captain America| 95         | Strength, fighting skills,fast   |     No   |
| Black Panther  | 94         | Rich, fighting skills, tech,fast |     Yes  |
| Bruce Banner   | 50         | (in)ability to turn into hulk    |     No   |

Many machine learning models must represent the features as real-numbered vectors since the feature values must be multiplied by the model weights.


- **Integer and floating-point data** don't need a special encoding because they can be multiplied by a numeric weight.

- **Categorical values** have a discrete set of possible values. For example, there might be a feature called **Capabilities** with options that include:

[fast, fighting skills, flying, inability to turn into hulk, magic, Rich, Strength, Spidersense, tech, teleporting, webbing, weapon making]

One hot encoding for ironman : [0,0,1,0,0,1,0,0,1,0,0,1]


| Super hero     | PowerRange | Capabilities                     | Snapified|
|----------------|------------|----------------------------------|----------|        
| Iron man       | 95.0       | [0,0,1,0,0,1,0,0,1,0,0,1]        |     No   |
| Dr. Strange    | 98.0       | [0,0,0,0,1,0,0,0,0,1,0,1]        |     Yes  |
| Spiderman      | 94.0       | [0,0,0,0,0,0,1,1,0,0,1,0]        |     Yes  |
| Captain America| 95.0       | [1,1,0,0,0,0,1,0,0,0,1,0]        |     No   |
| Black Panther  | 94.0       | [1,0,1,0,0,1,0,0,1,0,0,0]        |     Yes  |
| Bruce Banner   | 50 .0      | [0,0,0,1,0,0,0,0,0,0,0,0]        |     No   |

In **Sparse representation** only nonzero values are stored. In sparse representations, an independent model weight is still learned for each feature value, as described above.
