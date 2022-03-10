# Bootstrapping 1729 - 2: Dashboard(v1) - Community Roadmap

Of the 4 features, mentioned in the [previous article](https://www.notion.so/Bootstrapping-1729-1-Dashboard-v1-Overview-c4ec1ebe9d9744688d34b1eb88eb4657) I have decided to start with the community roadmap(**tech tree**) due to a few reasons:

1.  **Permissionless:** Building the other features such as community progress or in-community discoverability would have required me to have access to the Auth token of a discord bot that can actually scrape the messages and would have required me to display at least some proof of work to the 1729 team. This feature can be done on a solidity IDE without any permissions.
2.  **Novelty:** Everyone realizes that we require a tech tree (Balaji has only said it only a thousand times and many hackathons have been organized to build a tech tree), some people in 1729 too I am sure are trying to envision what our tech tree may look like. There is a huge debate on this as well on what tools do we need to use: MIRO, Asana, ClickUp, Notion, Taskade, Github Issues, Obsidian, Roam, and so on. However, not many people are talking about tech tree generators for a purely decentralized community and that is where I feel the value lies. Since this allows the web3 community to come up with a more flexible tech tree structure I feel this is more in line with the spirit of 1729.
3.  **Hardline Decentralization:** The tech tree in my opinion can be implemented in a completely decentralized manner from the very first version itself. Issue creation, issue linking, issue reward staking, and issue reward releasing. The only thing that remains to be seen is how reward allocation conflicts will be resolved among competing solutions for a particular problem statement (**node**) on the tech tree. This will allow our tech tree to be censorship-proof from day 1 itself and community-centric while allowing standard game-theoretic behavior to govern individual actions (such as issue selection).

---

### Implementation

-   **Frontend**
    
    -   Fetching the Roadmap(Tech Tree):
    -   Creating a Node:
    -   Viewing a Node:
    -   Filtering Nodes: 
      
-   **Backend**
    
    We envision the community roadmap as a directional acyclic graph. Each node in the graph is actually a smart contract that implements a particular interface. Each node stores a certain amount of reward value that various people can contribute to. When someone raises a claim about having completed the actual issue, the node creator (i.e. the owner of the underlying contract) processes the claim and the contract releases the amount appropriately. In order to hedge out the number of winners on a particular node, we can create sub-rewards as checkpoints in each node.
    

In later versions, integrations with Github2DAO can be considered.


There will be one main smart contract CommunityRoadmap.sol which represents deploys multiple instances of RoadmapNode.sol on-chain with the required parameters in the constructor. A sample implementation of both these smart contracts is shown below:
