# Developing Priority Intelligence Requirements @ Red Hat 

Making educated guesses on what is important and providing a dedicated effort to react to  requests for information from various stakeholders are good drivers for threat intelligence teams at an early stage of their maturity. However, if we want to be more confident when setting the scope of a data collection plan or the prioritization of our analytical deliverables, Priority Intelligence Requirements (PIRs) are an invaluable tool.

## Why we developed a new process at Red Hat
Every book or paper on “How to set up a CTI program” will tell you that you need PIRs, but no matter how detailed such a document is, they will rarely tell you how to do it. Still, there are a couple of existing approaches, but their fundamental flaw - from our point of view - is the assumption that you can identify the “crown jewels” of your organization and that you understand what type of threat actors could be motivated to attack them. This is difficult for larger organizations with diverse and dynamic portfolios of products and services or organizations that have not faced sustained cyber attacks. Furthermore, the resulting PIRs based on the existing approaches tend to be quite general, and often are not specific enough for any organization. Instead, the process focuses almost exclusively on external threats without clearly defined links to your organization and its assets.

## What is the Red Hat approach to the process
The basic assumption of the Red Hat approach was that part of the process will be a risk assessment exercise designed to help you understand what is important for your organization. We also wanted the resulting PIRs to answer WHAT could be attacked, by WHOM and HOW. 

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
- production pipeline

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

FINAL SCORE = ELEMENT value * TA μ value (TA1+TA2) * AV μ value (IAV1 + IAV2)

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
