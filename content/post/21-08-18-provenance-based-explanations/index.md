---
title: Cracking the black box
subtitle: How KCL researchers build a provenance-based system to make AI explainable
featured: true
summary: How KCL researchers build a provenance-based system to make AI explainable
slug: provenance-based-explanations
date: 2021-08-18
group: CYS
categories: ""
tags:
- provenance
- explainable-AI
draft: false
show_date: true
private: false
image:
  focal_point: "top"
---

## Introduction

AI and machine learning have been the subject of a great deal of controversy over the past couple of years: a steady outpour of cases [reveal](https://www.newscientist.com/article/2166207-discriminating-algorithms-5-times-ai-showed-prejudice/) how automated systems have [denied](https://news.berkeley.edu/story_jump/mortgage-algorithms-perpetuate-racial-bias-in-lending-study-finds/) bank loans to applicants on dubious grounds, [refused](https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G) job applications from under-represented groups or [recommended](https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm) harsher prison sentences for ethnic minority defendants. In many instances, existent biases would feed into automated systems and [perpetuate](https://www.nytimes.com/2019/11/19/technology/artificial-intelligence-bias.html) them with no obvious ill intent, which makes it hard to identify who is ultimately responsible for discriminatory practices. Today, the serious challenges of systems that make unfair decisions and are prone biases on the grounds of race, gender or health are being discussed widely in the media. 

To many decision makers and members of the public, automated systems seem to [operate](https://www.scientificamerican.com/article/demystifying-the-black-box-that-is-ai/) like a ‘black box’. This causes a real headache for public and private organisations that fear the legal repercussions of implementing flawed systems of this sort. The potential costs of high-profile court cases, both in financial and reputational terms, are considerable. Calls are mounting to deploy only systems that are [explainable](https://royalsociety.org/-/media/policy/projects/explainable-ai/AI-and-interpretability-policy-briefing.pdf) in that the reasoning behind machine decisions can be traced back and evaluated retrospectively. In the US, legislators currently [debate](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3615731) the ‘Algorithmic Accountability Act’ that would require organisations to conduct robust AI fairness checks. For the European Commission, explainability has [emerged](https://publications.jrc.ec.europa.eu/repository/handle/JRC119336) ‘as a key element for a future regulation’ of AI beyond existing measures enshrined in the GDPR, such as in Article 13 of the recently proposed [AI Act](https://iapp.org/news/a/a-look-at-whats-in-the-eus-newly-proposed-regulation-on-ai/). And in the UK, even the intelligence service GCHQ has joined the debate and promises to [build](https://www.gchq.gov.uk/files/GCHQAIPaper.pdf) on Explainable AI wherever possible. 

With explainability gaining so much traction and attention, the big-prize question emerges, how can it be achieved in practice? How can abstract demands for transparency and accountability translate into actual AI design principles? Explainability itself is an umbrella term for a whole bag of fine-grained concepts and several engineering approaches compete in this space. A team at KCL Informatics offers a unique perspective on the complex challenge of Explainable AI: if we wish to explain the decision a system makes, let’s take a closer look at the processes of how it gets there, how it has been configured in the first place and what kinds of data it uses. 


## KCL’s provenance-based approach

To make headway on this sizeable problem, the team of Prof Luc Moreau and Dr Trung Dong Huynh and their project partners from the University of Southampton collaborated with the UK’s Information Commissioner’s Office (ICO). They’ve set themselves the following challenge: can we build a proof of concept for an automated decision-making system that provides details of meaningful, interpretable decisions at each step of the way? Any such system would have to meet [Article 15](https://gdpr-info.eu/art-15-gdpr/) of the GDPR, which explicitly states that ‘data controllers’, i.e. anyone who collects and uses data, must be able to provide ‘meaningful information about the logic involved’ in automated decisions. ‘Leveraging technology to see how socio-technical systems are constituted is a way to address their inherent opacity, as long as the explanations that are generated support rather than substitute human intervention’, Prof Sophie Stalla-Bourdillon from the University of Southampton explains. ‘Provenance offers the possibility to de-construct automated decision-making pipelines and empower both organisations to reach a high level of accountability and individuals to take action and exercise their rights’.

Over the course of only a couple of months, the team has delivered some impressive results. ‘The idea was to use what we call provenance, i.e. we record all the information from the very beginning as well as the flow of data’, Prof Moreau explains, ‘and we use this to build explanations that address some important legal requirements’. The team used the W3C’s tried and tested [PROV-DM](https://www.w3.org/TR/prov-dm/) data model to build a knowledge graph for a hypothetical lender that makes semi-automated decisions about loan applications. Provenance maps and records in full the activities between all entities involved. The process of applying for a loan, the application being evaluated, and a decision being made all leave a substantial audit trail that can be used to query the system at a later stage about why it has proceeded in the ways it did. 

{{< figure src="fig-1.svg" caption="Details of the provenance knowledge graph for loan applications. [Source](https://dl.acm.org/doi/10.1145/3436897)." numbered="true" >}}
 
However, a full provenance record would be information overkill and of not much use to anyone. To make the system useful, the team identified 13 categories of potential explanation categories that the hypothetical loan pipeline could draw up. To produce targeted information, each category is mapped to a pre-defined explanation framework. Upon being queried, it adds the relevant parts from the provenance record to a Natural Language narrative template: the output is a piece of text which is intelligible to human readers and explains why, for instance, a loan application has been rejected. Users are presented with a detailed breakdown of all decision variables involved, and receive responses to possible questions that they may have regarding their loan application: 

{{< figure src="fig-2.png" caption="Example responses to possible questions that the provenance model returns. [Source](https://dl.acm.org/doi/10.1145/3436897)." numbered="true" >}}

Upon clicking on any of the above questions, the system provides a detailed account of the relevant nodes involved and their relationships, e.g. if the decision did in fact involve human oversight or not, and which credit scores were used. 


## What’s the impact been so far?

KCL’s provenance-based approach has caught attention from a range of experts in multidisciplinary teams. The initial findings and a technical report have been [published](https://dl.acm.org/doi/10.1145/3436897) in the peer-reviewed ACM journal Digital Government: Research and Practice. ‘On top of that we’ve also launched a [demo page](https://explain.openprovenance.org/loan/) for everyone to give it a go’, Dr Huynh adds. 

The ICO considers the findings of the project extremely important. So much so that they include the team’s work in their official recommendations for all organisations that collect and process data. Prominently placed on their list of guidelines for building an explainable data model, the ICO now showcases KCL’s provenance-based approach as an example. ‘We’re obviously very pleased that our work has been acknowledged by the ICO, and listed as one of the technical approaches to producing explanations’, Prof Moreau says. 

{{< figure src="fig-3.png" caption="Detail of the ICO [guidelines](https://ico.org.uk/for-organisations/guide-to-data-protection/key-data-protection-themes/explaining-decisions-made-with-artificial-intelligence/part-2-explaining-ai-in-practice/task-2-collect/) that feature KCL's provenance-based model as an example." numbered="true" >}}

In their work, Prof Moreau and his team draw on the deep expertise and wide-ranging areas of research at KCL Informatics in the domain of Artificial Intelligence. King’s College is home to the UKRI’s Centre for Doctoral Training in Safe and Trusted Artificial Intelligence ([STAI](https://www.kcl.ac.uk/informatics/research/safe-trusted-ai)), which is led by King’s in partnership with Imperial College London. KCL Informatics is also heavily involved in the newly launched UKRI flagship programme, the Trustworthy Autonomous System ([TAS](https://www.tas.ac.uk/)) Hub where Prof Moreau serves as Deputy Director. And the AI project [THuMP](https://thump-project.ai/) also seeks to advance state-of-the-art Explainable AI. The team’s provenance-based approach slots in nicely with KCL Informatics’ considerable AI portfolio. 


## Looking ahead: the next steps

Given the early successes and wide impact of the project there is no stopping the team at this point. Codenamed [PLEAD](https://plead-project.org/) – Provenance-driven and Legally-grounded Explanations for Automated Decisions – the project has evolved into a much larger activity. Partnering with the University of Southampton, Southampton City Council as well as industry partners Experian and Roke, Prof Moreau’s team aims to develop and extend the provenance-based approach to a whole range of legal requirements that UK businesses face. ‘In PLEAD, our aim is to operationalise the methodology and a software system called “Explanation Assistant”, to allow organisations to adopt the system and integrate it to address their business needs’, Prof Moreau elaborates.

Funded by the EPSRC with a grant of £600K, PLEAD seeks to deliver a dedicated Explanation Assistant tool for any UK data controller to vastly extend their explanation capabilities. The team has already a delivered a series of talks and published a set of papers on this issue, with targeted workshops scheduled for later this year. With demands for truly Explainable AI growing from legislators and civil society actors alike, PLEAD can’t deliver its tool soon enough: in the near term, businesses can expect a regulatory shakeup that will leave no more room for black box AI.
