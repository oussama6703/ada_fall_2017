## 2.1. Analysis of Patents related to Artificial Intelligence

In this section of the project, we tried to anaylze patents related to Artificila Intelligence (AI) in a  comprehensive manner. We structered the section in the form of question and answer so, for each research question we tried to answer there is a sub-section. Before answering any questions, we gathered all the patents related to AI from 1976 until 2017 along with informations about their inventors, citations, companies and belonging countries.

The method we followed to acquire AI patents is two fold. First, we only consider IPC category "G06" which corresponds to "Computing; Calculating; Counting". According to our researches this is the main category where AI patents fall under. In addition to AI patents, this category contains many others and therefore, we only considered patent that has one of the AI related keywords in their titles. These keywords are gathered from different sources[1](https://phrasee.co/ultimate-glossary-artificial-intelligence-terms/) [2](https://business.twitter.com/en/blog/artificial-intelligence-terms-marketers-need-to-know.html) and can be accessed from [here](data/ai_keywords.txt). We consider a patent related to AI if its description contains one of these keywords. And more information related to IPC categories can be found [here](http://www.wipo.int/classifications/ipc/en/).

As we mentioned earlier, PatensView allows requesting patents only up to 100'000 at a time, to be able to gather all AI patents, we needed to request them in monthly chunks for each year. It is also worth mentioning that, it is required to clean the dataset since it was a bit messy in its raw form. Structure of the resulting dataset can be seen Table 2.1.

| **ID** | **Title** | **Citations** | **Country** | **Organization** | **Inventor ID** | **Inventor Name** | **Year** | **Month** |
|------|------|------|------|------|------|------|------|------|
| 4001787 | Data processor for... | 11 | US | IBM | 3959777 | Milton Jay Kimmel 	 | 1977 | 1 |
| 3942153 | Document transport... | 3 | US | Recognition Equipment Incorporated | 3942153 | Jack E. Balko | 1976 | 3 |
| 3947817 | Optical character recognition... | 50 | US | Recognition Equipment Incorporated | 3947817 | Stanley C. Requa | 1976 | 3 |
| 3967241 | Pattern recognition system | 24 | JP | Ricoh Co. Ltd. | 3967241 | Ryuichi Kawa | 1976 | 6 |
| 3967243 | Character pattern normalization... | 17 | JP | Kabushiki Kaisha Photron | 3967241 | Ryuichi Kawa | 1976 | 6 |

*Table 2.1: Sample Rows from the Dataset of Artificial Intelligence Related Patents*

At this point, we have the required data to be able to start answering questions. We wanted start with a basic one.

## 2.1.1. Which are the most cited patents (by other US patents) within the field of artificial Intelligence?

In our initial analysis we observe that, the patent dataset has a field for number of times that a particular patent cited by other patents however, further analysis showed that this field based only on US patents. More clearly, the description of this field is as follows: "Number of times the patent was cited by other US patents". Consequently, we don't have information about citations from other countries and decided to restrict the scope of this question into citation made only by US patents.

Note that actual patents are not only from US, just the number of citation that a particular patent have is calculated only by citation of other US patents.

| **ID** | **Title** | **Citations** | **Country** | **Organization** | **Inventor Name** | **Year** |
|------|------|------|------|------|------|------|
| 5933822 | Methods for an information retrieval... | 599 | US | Microsoft Corporation | Lisa C. Braden-Harder | 1999 |
| 6055573 | Communicating with a computer based... | 598 | US | SuperMarkets Online, Inc. | Will H. Gardenswartz | 2000 |
| 6363160 | Interface using pattern recognition and tracking | 456 | US | Intel Corporation | Boon-Lock Yeo | 2002 |  
| 6430539 | Predictive modeling of consumer financial behavior | 392 | US | HNC Software, Inc. | Ted E. Dunning | 2002 |
| 8035624 | Computer vision based touch screen | 331 | US | Intellectual Ventures I LLC | Philip L. Gleckman | 2011 |

*Table 2.2: Sample rows from Artificial Intelligence Patents Rankings by Citation Numbers*

Because of space concerns we only put a sample from top-cited AI patents, the whole ranking can be reached from our [notebook](LINK REQUIRED).

Looking at the names of top cited patents, they potentially, have lots of usage areas. Take for example, *"Predictive modeling of consumer financial behavior"* patent, it would clearly, be beneficial for any kind of company that interests in financial behaviour of its consumers (which is pretty much any company). Therefore, the popularity of this patent and the situation that it is being used by many other patents is highly expected. This is true for other top-cited patents in this list.

Another expected situation is that if a patent is granted earlier than others then it should have more citation and this is the case for most of the top-cited patents however we also observe that there are some patents relatively new (e.g. 2002, 2011). This might be an indication of that innovations in this area still continues and there are many researches and technologies that are benefiting from these patents.

As we mentioned, we don't have information about number of citations that a patent get by other patents apart from citations by US patents. This means that we don't have a global picture of patent citations and for this reason, we decided restrict this part of our study to only analyzing top cited patents (as we did above). Since our study is not country specific, analyzing citation data we have would only be related to US and therefore  wouldn't align with the purpose our study. Next, we move into more detailed analysis of AI patents.

## 2.1.2. How much artificial Intelligence related patents granted through years and what its the ratio of them among other patents?

Related to above question, we also hope to investigate following ideas. We know from common knowledge that AI related researches increased and decreased again during past decades, can we observe this patern by analysing the number of patents granted through years (in 1900s)? AI is also, one of the most popular area of research in today's world. Will these popularity will fade away like it did in the past or the haracteristic of the popularity trend is different this time?

To answer this question, we calculated number of AI related patents for each year from 1976 until 2016. (At the time of analysis, data for 2017 was incomplete and not taken into consideration.) The corresponding figure is as follows.

<a id='number_ai_patents_by_year'></a>
![Image](img/number_ai_patents_by_year.png)
*Figure 2.1: Number of Artificial Intelligence Related Patents in Years*

From this figure, it seems that there are two periods of time where number of AI patents raised that are around 1986 and 2006. Other than these periods, the amount of AI related patent seems pretty steady. But considering that overall number of patents has also increased over years, to be able to see the whole picture and make a more complete analysis, we also need to check the percentage of AI patents among all patents through years (Figure 2.2).

<a id='percentage_ai_patents_by_year'></a>
![Image](img/percentage_ai_patents_by_year.png)
*Figure 2.2: Percentage of Artificial Intelligence Related Patents in Years*

There are couple of observations worth mentioning about these figures. **First** of all, above graph starts with a decline from 1976. We already know that AI was popular field of research at 1960s (e.g. Artificial Neural Networks invented in this period.) and its popularity started to decline around 1970s (because of insufficient computing power and datasets). Although, we don't have information of patents in 1960s, we can see that the graph starts with a steady line in 1976 then, rapidly declines in 1977. It continues to fall for 3 years until it hits the lowest value in 1980.
The rate in 1977 is only reached again in 1989 which is 12 years lates.  So, the graph confirms our knowledge about the popularity of AI researches in 1960s. With this information, we believe that it is safe to assume, percentage of AI patents is an indication of popularity in AI researches. **Another** interesting point is that percentage of AI patents dramatically increases from 1987 to 1994 then, stays steady about 3 years until it starts to decline again for 5 years, until 2002. The rate of AI patents in 1996 is only reached after 10 years later, around 2006. We can see that this trend is pretty similar to 1960s', it starts with a rapid increase, followed by a steady period then, a decrease for couple of years and in both situation, around 10 years had to past before the rate came back to where it was. In light of this information, we can try to analyze the **current situation**. We see that there is a dramatic increase on patent rates from 2002 to 2012 then, it stays about the same with minor fluctuations. The characteristic that increasing rapidly and entering into steady phase is pretty similar to what we observed in last decades however it seems that the steady phase are not followed by a decline since the rate starts to increase again in 2016. Although this might be an indication that popularity of AI related researches won't decline this time, it is still too early to infer that. The first two phases were similar to what has been observed in the past decades but it requires time (at least couple more years) to decide whether this time will characteristic of the trend will be different or not.

One other valuable observation is that the AI researches are dramatically increased over 40 years, it was around *30 per/year with 0.03 percentage* and it is around *700 per/year with a percentage of 0.12* now.

As the next step, we wanted to analyse inventors.

## 2.1.3. Who are the most prolific inventors in the field of artificial intelligence?

Since we already have the required data, we just calculated number of patents that delivered by each inventors. Top inventors with highest number of patents in a sorted order can be seen in the following figure.

<a id='prolific_inventors'></a>
![Image](img/prolific_inventors.png)
*Figure 2.3: List of Prolific Inventors in the Field of Artificial Intelligence*

There is not much to interpret about this table (since we are already analyzing related companies and countries in other parts of the study). However, here is some information about top AI patent holders which confirms that we are on the right track.

**[Philip Yu](https://en.wikipedia.org/wiki/Philip_S._Yu)** is an American computer scientist and Professor in Information Technology at the University of Illinois at Chicago, known for his work in the field of data mining.

**[Dharmendra Modha](https://en.wikipedia.org/wiki/Dharmendra_Modha3)** is an Indian American manager and lead researcher of the Cognitive Computing group at IBM Almaden Research Center. He is known for his pioneering works in Artificial Intelligence and Mind Simulation.

Now, we move into company-wise analysis of AI related patents.

## 2.1.4. Which companies are holding most artificial Intelligence related patents?

To answer this question, we grouped the dataset according to companies and sorted them by number of patents. The findings are as follows.

<a id='number_of_ai_patents_by_company'></a>
![Image](img/number_of_ai_patents_by_company.png)
*Figure 2.4: Companies Holding the most Artificial Intelligence Related Patens*

As expected, IBM who has the highest number of patents in all categories has also the most AI related patens. Microsoft and Google takes the second and third places which are two of the biggest technology companies that are also known for their interest in AI researches.

Although this figure reveals valuable information about companies that are highly active in AI researches, we also wanted to examine companies that devotes most of their resources into AI related researches and analyze the benefit of these researches to companies. More specifically, the question we want to answer is as follows.

## 2.1.5. Is there a relationship between investing in artificial intelligence researches and being among top companies (according to  Fortune 500 list)?

In order to find how much resources are invested in AI researches, we decided to calculate ratio of AI patents among all other patents that a company have for each company. We just calculated number of AI related patents for each company and already have the information about [overall number of patents](number_of_patents_by_companies) (from first part of our study). With these, we calculate the percentage of AI related patents  within companies (Figure 2.5)

One important point to note is that for some companies, it is the case that they only have couple of patents which are all related to AI so, percentage of AI patent for this company ends up being 100%. Since, we only insterested in big companies in this study, we decided to remove all the companies that has less than 1'300 patents in general. Basically, we are interested in big companies that are devoted some part of their resources into AI researches and the correlation between this investments and their ranks.

<a id='percentage_ai_patents_by_companies'></a>
![Image](img/percentage_ai_patents_by_companies.png)
*Figure 2.5: Ratio of Artificial Intelligence Related Patents among All Others by Companies*

This figure reveals the rankings of companies based on how much of their patents are related to AI and this intuitively means that how much of their resources devoted to AI researches.

Now, we wanted to see whether or not investing AI research would end up increasing the rank of a company. For this purpose we decided to match companies we found (by the number of AI patents) with the companies in [Fortune 500](http://fortune.com/2015/06/13/fortune-500-tech/) list. Note that within that list, we only take companies related to computer software and information systems into account since it is highly probable that only these companies made considerable amount of researches related to AI. The results are demonstrated in Figure 2.6.

<a id='percentage_ai_vs_fortune'></a>
![Image](img/percentage_ai_vs_fortune.png)
*Figure 2.6: Top Companies Invested in AI Researches and Their Presence in Fortune 500 List*

From this figure we can see that companies that invested in AI research more (which derived from proportion of AI patents they have) is more likely be in the Fortune 500 list. As the AI research proportion decrease chance of a company being among the top companies also, decreases. We can see that there is only one company in the Fortune list with less than 0.2 AI patent ratio which corresponds to rank 50 in our list (as seen in the figure). This means, all the technology companies (except one) in Fortune 500 list are from top 50 in the ranking we calculated by AI patent ratio.

For ease-of-read, here is the complete list of top AI invested companies that made it to the Fortune list (which are red dots above).

| **Organization** | **Ratio of AI Patents** |
|------|------|
| Yahoo! Inc. | 2.22 |
| Google, Inc. | 1.75 |
| Symantec Corporation | 1.69 |
| Oracle International Corporation | 0.96 |
| Facebook, Inc. | 0.87 |
| Amazon Technologies, Inc. | 0.85 |
| IBM | 0.69 |
| Xerox Corporation | 0.49 |
| NCR Corporation | 0.47 |
| Cisco Technology, Inc. | 0.41 |
| Hewlett-Packard Development Company | 0.40 |
| Nvidia Corporation | 0.25 |
| Qualcomm, Inc.| 0.22 |
| Intel Corporation | 0.18 |

*Table 2.3: Top Companies Invested in AI Researches and Their Presence in Fortune 500 List*

With that, the company-wise analysis is concluded and now, we can move into investigating countries.

## 2.1.6. Which countries have the most patents related to artificial intelligence?

We though that the best way to indicate the overall AI related patents that each countries while also displaying the change in number in years is use stacked bar chart (Figure 2.7). Note that, there is also an interactive visualization that displays number of AI related patent throughout years in our [notebook](LINK REQUIRED).

<a id='number_ai_by_countries'></a>
![Image](img/number_ai_by_countries.png)
*Figure 2.7: Countries that Has the Highest number of Artificial Intelligence Related Patens in Years*

From this map, it is clear that number of AI related patents has increase signiﬁcantly over years. We also, observe that United States and Japan takes the lead again and most of these countries are the ones known for their technological advancement. It is worth mentioning that although Isreal (IL) couldn't make it to the top in terms of [total number of patents](#last_year_patents_by_country), it is 5th country in AI related patents ranking. This situation is exceedingly interesting since Isreal is one of the most impactful countries in the Middle-east and AI researches might have an effect on that. We examine this idea more in the following section.

Similar to [the map we draw](#patents_by_country) in the first part of the project, we wanted draw a choropleth map to be able to see the distribution of AI related patents around the world. As before, we used logarithmic scale to assign colors to the countries. Resulting map can be seen in the following screenshot and we served the interactive visualization of this map in [here](html/ai_patents_by_country.html).

<a id="ai_patents_by_country"></a>
![Image](img/ai_patents_by_country.png)
*Screenshot 1: The Choropleth Map according to Number of AI Related Patents*

Last question we wanted to answer is related to a recent statement made by *Putin* which is “the nation that leads in artificial intelligence will be the ruler of the world”.

## 2.1.7. What is the relationship between number of artificial intelligence related patents that countries have and the rank of their defence industries?

To be able to answer this question we needed a reliable ranking for countries' defense industries. We though that using [Global Defense Companies 100](http://people.defensenews.com/top-100/) list (from Defense News), to extract the revenues of defense companies along with belonging countries then, grouping these companies by countries and summing up their revenues would give us a reasonable estimation for defense industry rankings of countries. The ranking (top 10) we calculated can be seen in Table 2.4.

| **Country** | **Revenue (in Milions)** |
|------|------|
| US | 220693 |
| GB | 40529 |
| FR | 27931 |
| RU | 19428 |
| IT | 9832 |
| JP | 8664 |
| IL | 8615 |
| KR | 7650 |
| IN | 3682 |
| DE | 3421 |

*Table 2.3: Defense Industry Ranking of Countries according to Revenues retrieved from Defence News*

Our prior analysis showed that similar to company analysis, only half of countries made it to the top defence industries list. Consequently, we decided to follow the same method as before and check which countries from our top list (based number of AI patents) made it to the top defence industries list.

One other point to mention about our choice of implementation is that unlike companies, we are not going to use AI patents ratio since we observed that calculating percentages were not really descriptive in country-wise analysis. There are a lot of countries with very few patens and just a few countries with a lot of patents (as you can see in the [figure we draw](#number_ai_by_countries)) and therefore, pruning according to certain number of patents doesn't work here. We only excluded United States and Japan to be able to demonstrate rankings of other countries more clearly. Note that we already know both US and JP are on the top defence industries list.


<a id='percentage_ai_vs_defence'></a>
![Image](img/percentage_ai_vs_defence.png)
*Figure 2.8: Countries that have Highest number of AI Related Patents and Their Presence in Top Defence Industries List*

Again, it is obvious that countries that have more AI related patents are much more likely to be in top defence industries list. 16 out of 47 countries (in our list based on AI related patents) were also made it to the top defence industries list. Moreover, the figure reveals that 13 of these 16 countries has more than 10 patents in AI. It can also be seen that 15 out of top 20 countries in our list (based on AI related patents) were present in top defence industries list. It can also be seen from the figure, the frequency of red dots (countries in top defence industries list) increasing as the number of the AI related patents increase.

As a result, we can actually confirm that countries which are making more revenue from their companies in defense industry (meaning that countries which have better defense industries) are also the ones which have more AI related patents. So, as Putin stated, it seems that countries who invest in AI are the potential leaders of the future. However, it also seems that Putin won't be able to make it to the list ;)

| **Country** | **Number of AI Patents** |
|------|------|
| US | 4526 |
| JP | 807 |
| . | . |
| . | . |
| . | . |
| RU | 6 |
