# Developing Priority Intelligence Requirements @ Red Hat v1.1

In the rapidly evolving landscape of cyber threat intelligence (CTI), the formulation of Priority Intelligence Requirements (PIRs) stands as a crucial component of your CTI program and the planning and direction phase of the intelligence cycle. As a cyber threat intelligence analyst, you are likely familiar with the challenge of balancing limited resources within small CTI teams against the colossal task of delivering relevant, actionable information to decision-makers and stakeholders. This dilemma often leaves teams grappling with a choice: should they adopt a reactive stance, responding to emerging threats as they arise, or should they lean towards more proactive long term priorities. Integration of PIRs as a guiding principle will assist your program to pursue proactive strategic priorities more confidently without abandoning your reactive capabilities. This approach doesn't just enhance traditional functions like research, investigation, analysis, and reporting but also elevates advanced practices such as threat-informed defense, including threat hunting and detection engineering. 
In this blog post, we delve into this pivotal process as we unravel the significance of PIRs in shaping a more effective and strategic CTI function, thereby enabling your team to make a more substantial impact within your organization.

## Retired v1.0
The original Red Hat process was structured around two distinct risk assessment exercises, one focusing on internal factors and the other on external ones. These exercises were then combined into a mapping exercise, from which we derived a cohesive set of PIRs. The goal was ambitious: to address the 'What', 'Who', and 'How' of the threat landscape. 'What' referred to the data and infrastructure of our organization; 'Who' encompassed high-level descriptions of threat actors like state actors, organized crime, or hacktivists; and 'How' partly included types of initial access vectors.

![PIRs process v1.0](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/PIRs_process_v1.0.png)

On paper, the threat actor (TA) categorization and initial access vectors (IAV) presented well, offering a seemingly comprehensive story when presenting PIRs to stakeholders. However, as we repeatedly scaled this exercise across organizations, we encountered significant challenges. The process was labor-intensive, adding weeks of work and dozens of hours for the team, yet it didn't yield the expected value in operationalization. We also found that the general categorization of threat actors and initial access vectors lacked the depth needed for operationalization. What was missing was a finer granularity, like Tactics, Techniques, and Procedures (TTPs), and associated MITRE ATT&CK categorization. Recognizing this gap, we shifted our focus to aspects that provided more substantial inputs for the operationalization of PIRs.

## Overview of the process
This is a five-step process: Step 1, identifying key organizational elements from strategic documents; Step 2, mapping these elements to supporting assets; Step 3, linking elements with types of adversarial operations using a custom classification; Step 4, assessing risks using a likelihood/impact matrix to determine the appeal of elements to attackers; and finally, Step 5 customizing PIRs into actionable intelligence requirements. 

![PIRs process v1.1](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/PIRs_process_v1.1.png)

## A STEP-BY-STEP GUIDE

#### STEP 1: Extracting Organizational ELEMENTS
The initial step involves identifying the core elements of your organization. These elements are not directly related to information security but are crucial in defining your organization's identity. They are derived from high-level strategic documents, such as annual reports, business strategies, senior leadership communications , and even the 'About' section of your website. These documents contain keywords, topics, or short sentences that encapsulate your organization's strategy, mission, and vision.

**Questions that can help you to define ELEMENTS of your organizations:** 
- What features define your organization?
- What makes your organization unique?
- What are the most important aspects of your strategy?
- Why is anyone buying your products or services?
- What is your competitive advantage? How do you compare to your competitors?
- Are certain products or services more important than others?
- What valuable data do you have? Is there data that keeps you ahead of competitors, proprietary information, R&D, data on relations with partners or customers, or data that would cause damage if released?
These elements should describe the essence of your organization, including both obvious and subtle aspects. They define what makes your organization unique, why customers choose your products or services, and what sets you apart from competitors. This also includes valuable data like proprietary information, R&D, partner relationships, and sensitive corporate information.

**Examples of the elements for a fictitious electric vehicle producer Stellar Electric[^1]:**
EU-based, electric vehicle industry company with revenue over 1 billion EUR
Research and Development in EU and China drives the company success
Car production in EU and China
Limited battery production capacity
Supply chain spans multiple countries, including China and Chile. 
Proprietary range-boosting technology: 20% longer range compared to competitors
Public perception of Stellar environmental impact is vital to the brand reputation       
Software-first approach; proprietary In-vehicle software
Advanced safety features 

**Sub-STEP: FUNCTION**
Linked to these elements is a sub-step called 'Function.' It ties the elements back to information security by clarifying what needs to be protected from an information security standpoint. For example, if an element is 'limited battery production,' its function might be ensuring continuous battery production. This context helps in understanding the element from an information security perspective and guides the subsequent risk assessment exercise.

**Output:** Sheet listing the ELEMENTS and FUNCTION of the ELEMENTS of your organization

![Examples of the Elements and Function for Stellar Electric](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/Function.png)

#### STEP 2: ASSETS Mapping to Elements
Once you have defined your organizational elements, the next step is to map the supporting technology, data, or information to these elements. This step can be high-level or detailed, depending on your approach. For instance, if your element is operational technology supporting battery production, the key asset might be the Operational Technology and Industrial Control Systems that keep the production running. For proprietary technologies, the critical asset could be the documents containing proprietary information.
This step is about linking the abstract elements of your organization to tangible assets. It's a crucial bridge between the theoretical understanding of your organization and the practical aspects of protecting it. When developing PIRs at Red Hat, we kept this high-level, avoiding overly specific details from Configuration Management Databases or similar documentation, which can be overwhelming and too detailed for this exercise.

![Examples of the Supporting Assets](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/Assets-types.png)

These two steps form the foundation of a robust CTI process, aligning your organization's essence with its security needs, and setting the stage for mapping of adversarial threat operations and risk assessment in the next steps.

![Examples of the Elements, Function and Assets for Stellar Electric](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/Assets.png)

**Output:** “Supporting ASSETS” column in the Sheet listing the ELEMENTS of your organization

#### STEP 3: Linking ELEMENTS with Types of Adversarial Operations
This step involves connecting the previously identified organizational elements with specific types of adversarial operations. We found that existing classifications of cyber attacks didn't quite fit our needs, leading us to develop our own classification. This classification focuses on the impact of cyber attacks on business operations and also on applicability of the terms used in the classification in threat intelligence platforms (TIPs), which is vital for operationalization. So for example, we use the relatively vague term “ransomware” instead of more precise variants, because that is a term that will more likely provide search results in TIPs. Types of operations in our classification include ransomware, espionage, financial fraud, denial of service, and “downstream” supply chain attacks where your organization is a target rather than supply chain as an initial access  vector.

![Types of Adversarial Operations, corresponding MITRE ATT&CK techniques and keywords](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/Types-of-adversarial-operations.png)

If this classification doesn't suit your needs, existing frameworks like MITRE ATT&CK, STRIDE, VERIS Framework, CAPEC, or ENISA and FIRST taxonomies can be utilized. Alternatively, attacks can be categorized based on their impact on confidentiality, integrity, and availability.

**Output:** Types of adversarial operations linkend to the ELEMENTS of your organization

#### STEP 4: Risk Assessment Using Likelihood/Impact Matrix
The fourth step involves a risk assessment exercise using a likelihood/impact matrix. This step aims to foster a specific mindset towards risk assessment. We refer to 'likelihood' as 'appeal,' especially when communicating with non-InfoSec personnel, as it aids in understanding the exercise. The focus is therefore on determining the attractiveness of an element or asset to attackers and the potential consequences of a compromise.

 ![The options for likelihood (appeal) and impact questions](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/RiskAssessment-options.png)

**Output:** Scored and ranked ELEMENTS, FUNCTIONS, ASSETS and Types of Adversarial Operations 

 ![The final risk score for each ELEMENT will assist you in ranking of the PIRs](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/RiskAssessment.png)

#### STEP 5: Customization of the PIRs
At the end of the risk assessment exercise, you'll have a ranked list of the top five or top ten elements - depending on your appetite for a number of PIRs - along with the mapped types of adversarial operations. This last step involves determining the format of the final PIRs. Will they be short statements, intelligence questions, requests for information, or something else? We opted to keep it straightforward at Red Hat and use the ranked elements in their original form.
Occasionally, you may need to rephrase results into more actionable statements. For instance, an element like “EU-based, electric industry company with revenue over 1 billion EUR” might be translated into a more intelligible PIR, such as “Threats to STELLAR based on its revenue, geography, industry, and market position.”
This comprehensive process ensures that PIRs are not only tailored to the specific needs and characteristics of your organization but also actionable and relevant in the context of your security posture.

 ![Examples of PIRs of Stellar Electric](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/PIRs-final.png)

**Output:** PIRs

## Scaling the process to multiple respondents
If you want to ensure objectivity and limit the bias by individual analysts or individual teams, you will prefer to conduct the exercise on a larger scale. You should ideally engage multiple CTI stakeholders, including respondents with good knowledge of the business side of your organization in the mapping (STEP 3) and risk assessment exercise (STEP 4). The sheet for PIR development is designed for a single respondent, so in case of multiple respondents it's necessary to calculate median or average scores and manually rank the PIRs.  
None of the subjects of the risk assessment exercises, such as your organization’s strategy, the threat actors or initial access vectors, are immutable. Periodical review of the PIRs is a necessary part of the process. On the other hand, even though the threat environment is highly dynamic and ever changing, your high-level PIRs should be relatively stable unless your organization is undergoing a major transition. 
 
## Process of iterations and gradual improvement
To define the ELEMENTS and pose the right question that can be understood the same way across multiple stakeholders is not trivial. It is rather difficult to achieve the perfect PIRs process in year one. You might prefer to see the first attempt as a trial and seek inputs only from a selected number of stakeholders across your organization. Make sure they understand the questions and the risk assessment exercises the way you intended and try to collect as much feedback as possible. Use the lessons learned during the next iteration and engage a broader spectrum of people from your organization to get new perspectives and to avoid bias that your team could have. 
PIRs will offer you not only a tool for your Cyber Threat Intelligence program, but the process of developing them will provide you and your team a great learning opportunity to explore your organization, engage with multiple teams across it, and investigate the relevance of a wide spectrum of threats to your attack surface and industry. 

## Red Hat PIR development process v1.1 template
You can make a copy and customize the [the Red Hat PIRs process v1.1 template](https://docs.google.com/spreadsheets/d/1lnZOGX6Shm4NoT06APeRPXe4jEX0dCWDXTrmm60aOa8/edit?usp=sharing)

[^1]: Annual Report of mock-up company [Stellar Electric](https://drive.google.com/file/d/1gJ9s6ergncUr5LK_6s8HUwtQJOksD_lq/view)
