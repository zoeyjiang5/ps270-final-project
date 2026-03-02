PEW RESEARCH CENTER
Wave 154 American Trends Panel 
Dates: Sept. 3-15, 2024
Mode: Web and CATI
Sample: Subsample plus SSRS Opinion Panel oversample of Hispanic and non-Hispanic Black adults
Language: English and Spanish
N=6,204

***************************************************************************************************************************
NOTES

Wave 154 includes an oversample from the Opinion Panel (OP). A set of questions are asked only of the OP respondents towards the end of the survey. They are used for weighting and analytical purposes. They align with existing measurements for ATP respondents so that the samples can be combined. The public use dataset does not contain these raw demographic questions. Instead, demographic information from OP and ATP respondents are combined into variables denoted with “F_” (e.g. F_GENDER, F_AGECAT) and can be found towards the end of the variable list in the dataset.

This dataset contains the variables corresponding to questions asked in the survey. It also contains administrative data, such as the main production weight and completion date. There are several types of additional variables that we can typically provide upon request, if they were created for published reporting: 
(1) Researcher-created variable(s) reflecting how we categorized responses to open-ended questions. We do not release verbatim answers to open-ended questions, in the interest of protecting panelist anonymity.
(2) Researcher-created variables needed to replicate published analysis (e.g., an index using several questions).
(3) Special weights needed to replicate published analysis. The main production weight is included in the public dataset. Special weights refer to those used for unusual, bespoke analysis. We can provide existing special weights upon request so long as the analysis they support does not pose a risk to panelist anonymity.

For a small number of respondents with high risk of identification, certain values have been randomly swapped with those of lower risk cases with similar characteristics.

BOYS/GIRLS
Both BOYS and GIRLS were asked of all respondents in order to give them the opportunity to weigh in on raising both boys and girls. However, these questions are subject to strong order effects, so we only analyzed data based on the question asked first. The data for BOYS only includes respondents who saw the BOYS battery first, and the data for GIRLS only includes respondents who saw the GIRLS battery first.  

MASCFEM
The W154 dataset contains the MASCFEM created variable which is a scale derived from respondents’ self-reported masculinity and femininity. For details on how this variable was created, see https://www.pewresearch.org/social-trends/2024/10/17/how-men-and-women-rate-their-own-masculinity-and-femininity/ 


***************************************************************************************************************************
WEIGHTS 


WEIGHT_W154 is the weight for the sample. Data for all Pew Research Center reports are analyzed using this weight.


***************************************************************************************************************************
Releases from this survey:

March 13, 2025 "U.S. adults differ in how much they say certain things should be emphasized for boys and girls"
https://www.pewresearch.org/short-reads/2025/03/13/us-adults-differ-in-how-much-they-say-certain-things-should-be-emphasized-for-boys-and-girls/

January 24, 2025 "U.S. teens are less likely than adults to know a trans person, more likely to know someone who’s nonbinary"
https://www.pewresearch.org/short-reads/2025/01/24/us-teens-are-less-likely-than-adults-to-know-a-trans-person-more-likely-to-know-someone-whos-nonbinary/

January 16, 2025 "Men, Women and Social Connections"
https://www.pewresearch.org/social-trends/2025/01/16/men-women-and-social-connections/

November 19, 2024 "Views of DEI have become slightly more negative among U.S. workers"
https://www.pewresearch.org/short-reads/2024/11/19/views-of-dei-have-become-slightly-more-negative-among-us-workers/

October, 17, 2024 "How Americans See Men and Masculinity"
https://www.pewresearch.org/social-trends/2024/10/17/how-americans-see-men-and-masculinity/

***************************************************************************************************************************
SYNTAX

**SYNTAX FOR MASCFEM VARIABLE**

RECODE MASCSCALE_W154 (1=4)(2=3)(3=2)(4=1)(5=0)(99=99) INTO MASCSCALEREC.
RECODE FEMSCALE_W154 (1=4)(2=3)(3=2)(4=1)(5=0)(99=99) INTO FEMSCALEREC.
DO IF (MASCSCALEREC<99) AND (FEMSCALEREC<99).
COMPUTE MASCFEM_W154=MASCSCALEREC - FEMSCALEREC.
END IF.
IF ((MASCSCALEREC=99) OR (FEMSCALEREC=99)) MASCFEM_W154=99.
EXECUTE.
VARIABLE LABELS MASCFEM_W154 'Combined masculinity-femininity scale'.
VALUE LABELS MASCFEM_W154 
    4 '4 - Extremely masculine, not at all feminine' 
    3 '3' 
    2 '2' 
    1 '1' 
    0 '0 – Equally masculine and feminine or neither' 
    -1 '-1' 
    -2 '-2' 
    -3 '-3' 
    -4 '-4 - Extremely feminine, not at all masculine' 
    99 ‘Refused MASCSCALE or FEMSCALE’.
EXECUTE.





