# Developing Priority Intelligence Requirements @ Red Hat v1.1

In the rapidly evolving landscape of cyber threat intelligence (CTI), the formulation of Priority Intelligence Requirements (PIRs) stands as a crucial component of your CTI program and the planning and direction phase of the intelligence cycle. As a cyber threat intelligence analyst, you are likely familiar with the challenge of balancing limited resources within small CTI teams against the colossal task of delivering relevant, actionable information to decision-makers and stakeholders. This dilemma often leaves teams grappling with a choice: should they adopt a reactive stance, responding to emerging threats as they arise, or should they lean towards more proactive long term priorities. Integration of PIRs as a guiding principle will assist your program to pursue proactive strategic priorities more confidently without abandoning your reactive capabilities. This approach doesn't just enhance traditional functions like research, investigation, analysis, and reporting but also elevates advanced practices such as threat-informed defense, including threat hunting and detection engineering. 

In this blog post, we delve into this pivotal process as we unravel the significance of PIRs in shaping a more effective and strategic CTI function, thereby enabling your team to make a more substantial impact within your organization.

## Retired v1.0
The original Red Hat process was structured around two distinct risk assessment exercises, one focusing on internal factors and the other on external ones. These exercises were then combined into a mapping exercise, from which we derived a cohesive set of PIRs. The goal was ambitious: to address the 'What', 'Who', and 'How' of the threat landscape. 'What' referred to the data and infrastructure of our organization; 'Who' encompassed high-level descriptions of threat actors like state actors, organized crime, or hacktivists; and 'How' partly included types of initial access vectors.


> "If you know the enemy and know yourself, you need not fear the result of a hundred battles" 
> Sun Tzu, The Art of War

We knew from the beginning that the starting point of the process has to be that we “know ourselves”, but how to achieve this? Are there existing documents or processes that could help us? As information security practitioners we would be looking at data and system classification documents, lists of critical applications and business processes, but it became apparent that these are too low level and don’t provide a good perspective on what we, as a company, care about and where a potential attack would hurt the most. We decided to take a different approach; similarly to government entities that would build PIRs based on available higher-level strategic documents, we reviewed our business strategy, documents describing who we are as a company, as well as company-wide briefings and communications from our senior leaders during which they shared business priorities. We used this information to extract keywords that define various aspects of the organization such as the mission and vision, the business strategy, and core values. We call these keywords ELEMENTS.

## Overview of the process  
The Red Hat process is based on two relatively simple risk assessment exercises divided by  internal and external focus. These two exercises are then merged in a mapping exercise and translated into a coherent text to determine the actual PIRs. Additional parts of the process can be a stakeholder review, approval by senior executives, and annual review of the PIRs.

![Red Hat PIRs development process](https://github.com/redhat-infosec/priority-intelligence-requirements-dev/blob/main/PIRs_process_Blog-post.png "Red Hat PIRs development process")

## A STEP-BY-STEP GUIDE

#### Step 1 (INTERNAL FOCUS) core ELEMENTS of your organization’s business and strategy 
Extract keywords representing your organization, its strategy, mission and vision from high-level strategic documents defining your organization and depicting your organization’s strategy.

Examples of the keywords:
- Open hybrid cloud built on the technological foundation of Red Hat Enterprise Linux, Red Hat OpenShift, and Red Hat Ansible Automation Platform. 
- Custodian of corporate information
- Hybrid work model
- Open and inclusive culture

**Output:** Sheet listing the ELEMENTS representing your organization and its strategy

#### Step 2 (INTERNAL FOCUS) ASSETS and technologies in support of the ELEMENTS 
Map the most important ASSETS and technologies of your organization to the ELEMENTS (See Step 1). We used high-level descriptions of our infrastructure, products, services, information assets, third party products, third party services, etc. because the existing technology and information asset management documentation is too detailed.  

Example: 
- third-party services
- customer entrusted data
- employee PII
- production pipeline [^3]

**Output:** “Supporting ASSETS” column in the Sheet listing the ELEMENTS representing your organization and its strategy (see Step 1)

#### Step 3 (INTERNAL FOCUS) ELEMENTS risk assessment exercise 
Use the sheet with the list of ELEMENTS and supporting ASSETS for the exercise, assessing the likelihood and impact of a potential attack on the supporting ASSETS and the ELEMENTS. Collect inputs from a wide spectrum of stakeholders in your organization. Use the median score for each ELEMENT. Rank the ELEMENTS by the median score and use the top 10 ELEMENTS for the mapping exercise (Step 5). 

**Output:** Scored and ranked ELEMENTS and your top 10 ELEMENTS 

#### Step 4 (EXTERNAL FOCUS) Threat landscape risk assessment 
List generic types of threat actors (TA). You can go into more detail and work with specific threat groups and individual actors at a later stage when you are developing Specific Intelligence Requirements (SIRs) which you derive from the PIRs.   

Example:
- state actors
- cybercriminals
- hacktivist

List generic types of initial access vectors (IAV)

Example:
- social engineering
- vulnerability exploitation
- supply chain attack

Assess the risks of each TA and IAV for your organization. Consider the impact of a potential attack, likelihood of attack in the next two years and current targeting of the TA or relevance of the IAV vector for your organization. Collect inputs from a wide spectrum of stakeholders in your organization. Use the median score for each TA and IAV. Rank the TA and IAV by the median score and use the top 5 TA and top 5 IAV for the mapping exercise (Step 5) 

**Output:** Scored and ranked TA and IAV and your top 5 TA and top 5 IAV

#### Step 5 Mapping exercise 
Map the two most relevant TA and IAV from the list of top 5 TA and IAV to each of the top 10 ELEMENTS.

Methodology: Focus Group Discussion (FGD) > agreed result (no median scoring etc.)

FINAL SCORE = ELEMENT value [^4] * TA μ [^5] value (TA1+TA2) * AV μ value (IAV1 + IAV2)

**Output:** Ranked list of ELEMENTS with mapped TA and IAV = your PIRs in the form of keywords

#### Step 6 Translate the ranked ELEMENTS with mapped TA and IAV to PIRs
Use the ranked list of Top 10 ELEMENTS with mapped TA and IAV to generate the PIRs. The PIRs can be in any form that is appropriate for the intended operationalization: short statements, intelligence questions, requests for information etc. 

**Output:** PIRs

## Adjust the process to your organization’s needs 
If you know the “crown jewels” of your organization well, you can do just the external threat landscape assessment. If you are unclear on what the “crown jewels” of your organization are and you have people available who understand both the organization and the threat landscape, you can do a single combined INTERNAL and EXTERNAL exercise in which you immediately map the threat actors and initial access vectors to the ELEMENTS. You can easily adjust the process to your organization’s needs.
Possible additional steps in the above described PIR development process include a stakeholder review of the PIRs that could generate additional insights. The PIRs can also be consulted and approved by an appropriate senior executive, if this is something that could help the implementation of the PIRs into your organization’s intelligence cycle.  
None of the subjects of the risk assessment exercises, such as your organization’s strategy, the threat actors or initial access vectors, are immutable. Periodical review of the PIRs is a necessary part of the process. On the other hand, even though the threat environment is highly dynamic and ever changing, your high-level PIRs should be relatively stable unless your organization is undergoing a major transition. 
 
## Process of iterations and gradual improvement
To define the ELEMENTS and pose the right question that can be understood the same way across multiple stakeholders is not trivial. It is rather difficult to achieve the perfect PIRs process in year one. You might prefer to see the first attempt as a trial and seek inputs only from a selected number of people across your organization. Make sure they understand the questions and the risk assessment exercises the way you intended and try to collect as much feedback as possible. Use the lessons learned during the next iteration and engage a broader spectrum of people from your organization to get new perspectives and to avoid bias that your team could have. 

If you follow the above described process, the PIRs will offer you not only a tool for improvement of your Cyber Threat Intelligence or Threat Hunting program, but the process of developing them will provide you and your team a great learning opportunity to explore your organization, engage with multiple teams across it, and investigate the relevance of a wide spectrum of threats to your attack surface and industry. 

## Red Hat PIR development process template
You can make a copy and customize the [the Red Hat PIRs process  template](https://docs.google.com/spreadsheets/d/1ux_7epS3AWPQO_CKDV90n4u3G4Tk1kZ_LYSuQqve76w/edit?usp=sharing) to make it work for your organization.

[^1]: The most elaborated publicly available process I’m aware of was developed by [Intel471](https://intel471.com/resources/cu-girh-download-request)
[^2]: To be more precise, by HOW we mean what could be the initial access vector.
[^3]: At Red Hat we worked with 25 ELEMENTS.
[^4]: Top 1 TA and IAV will have value 5, …Top 5 TA and IAV will have value 1; Top 1 and 2 ELEMENTS will have value 5, …Top 9 and 10 ELEMENTS will have value 1.
[^5]: Mean of the values of the two TA and mean of the values of the two IAV. 
