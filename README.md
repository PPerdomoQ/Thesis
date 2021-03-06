# Duchenne Muscular Dystrophy Drug Reourposing using Knowledge Graphs and eXplainable AI

In this repository you will find the code necessary to run the pipeline shown in: *TODO: Add paper*. This pipeline is part of a Master Thesis project and it is expected to be improved throughout time. 

The objective of this project is that, given a number of seeds related to a target (rare) disease, several drug candidates and **explanations** will be obtained for the symptoms of the targeted disease. *TODO: Add pipeline*

In total, three Jupyter Notebooks are used to obtain the predictions and the explanations. The first one, *TODO: Add file*, is used to create a Knowledge Graph containing information of the disease. In this first notebook, only information from Monarch *TODO: Add link*, is used. To incorporate drug information (Drug-Target and Drug Disease) the second notebook, *TODO: Add file*. This notebook incorporates information from DrugCentral and Therapeutic Terget Database. The final notebook, *TODO: Add file*, is the one that provides the predictions and the explanations. Each notebook contains information about its use, but in the next sections there is a small summary showing its details.

## Graph building (Monarch)

In this first part, the Knowledge Graph is created using information from Monarch. To extract information from Monarch, Bioknkwledge Reviewer is used. As input you will need a number of seeds of the targeted diseases. The seeds are the IDs used by Monarch to identify its elements. You can use the Monarch interface to search for the seeds *TODO: Add link*. In our example, we have used seeds of Duchenne Muscular Dystrophy (*TODO: Add seeds) and the gene affected innthe disease: *DMD* (*TODO: Add seed*). As output, two *.csv* files are obtained, one containing the nodes of the Knowledge Graph and one containing the edges of the Knowledge Graph. 

## Graph building (DrugCentral and TTD)

The second part is to incorporate drug information from DrugCentral and TTD. As input, this notebook receives the two *csv* files generated in the previous step, a *csv* file containing information from DrugCentral (downloaded from *TODO: add link), a *txt* file containing information from TTD (downloaded from *TODO: Add link*) and a file matching TTD IDs to Monarch IDs (this file corresponds to *TODO: Add file*, and was obtained using SORTA *TODO: Add link*. As output this notebook produces two *csv* files, one containing all the nodes of the Knowledge Graph and one containing all the edges of the Knowledge Graph.

## Predictions and Explanations

In this final part predictions and explanations are obtained. To obtain predictions a Graph Neural Network (GNN) model was build. This model was created using *Pytorch Geometric* and *DeepSnap*. To obtain the explanations a modified version of GNNExplainer is used. This modified version is allows for explanations on a link prediction task. As input, this notebook receives the two *csv* files obtained in the previous step, and as output in provides a list of drug candidates for each symptom of the disease and a list of explanations supporting these predictions. 
