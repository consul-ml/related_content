# Related content clustering and Tags generation


For general information about this machine learning project visit: https://github.com/consul-ml/consul-ml

This repository contains the **Natural Language Processing** scripts to generate related content and tags for the Consul platform. The code and experiments related are detailed in https://arxiv.org/abs/2103.00508

This code can be used for the Citizen proposals and/or the Participatory Budgeting features of Consul. Independent scripts are provided for each feature.

The scripts generate for each citizen proposal / budget project:

* Tags.

* List of related content.

All existing proposals are analysed, and categorised in groups according to their texts. Each proposal is assigned the Tags that better represent the group where it belongs (or the combination of groups, for proposals of mixed topics). Additionally, the analysis allows to determine how similar the proposals are, and thus to create for each proposal a list of the other most similar proposals.

The scripts will also generate useful analysis files as for example: "`ml_repr_props.csv`" A file listing the most representative proposals for each of the groups.

The technique used here is Non-Negative Matrix Factorisation, as explained in detail in the article at the top.

## How to install this code

The AI/Machine Learning module of Consul is included by default in the installation of Consul, but needs to be activated to use it. In order to do so, please follow the instructions in the module [Administration interface -> AI/Machine Learning -> Help]

To use this "related content and tags" code:

1) Copy the corresponding .py files (proposals and/or budgets) to the `public/machine_learning/scripts/` folder of your server.

2) Copy the corresponding .ini files to the `public/machine_learning/data/` folder of your server.

3) Install the Python requirements needed by running "`pip -i requirements.txt`" on the server.


## Settings

The settings of the code can be changed by modifying the .ini files. Open the file with a text editor and change any of the settings. Remember to upload the modified version to your server.

Next are presented the most relevant options:
* `numb_related_proposals = 2` / This number defines how many similar proposals will be listed for each proposal. In this case, it will list the top 2 most similar proposals.
* `numb_topics = 3` / This setting establishes the number of different groups in which to organise the proposals. Here the proposals would be organised in 3 groups.
* `numb_topkeywords_pertopic = 5` / This setting sets how many Tags should be assigned to each proposal. By default 5 Tags.
* `n_top_represent_props = 2` / This option defines how many proposals will be listed in the "representative proposals" file explained previously ("`ml_repr_props.csv`")

## Using the code

To use the code (after following the instructions in the section "How to install this code") open the Administration interface of Consul and click in the "AI / Machine Learning " tab on the bottom left of the menu.

The module will display by default the "Execute script" tab. Select the script to be executed and press the button. It will take some time to run depending on the amount of content on the platform. Once finished it will show a message "The script has been executed successfully." (you will need to refresh the page to see the message). 

Proceed to the "Settings / Generated content" tab. If the execution was successful you will see a button under the corresponding section "Tags", "Related content", or "Comments summary". Just click on the button to activate the generated content in the platform. All the contents can be deactivated just by clicking on the same button.

In the Help tab you can find more information about the module and how to use it.

