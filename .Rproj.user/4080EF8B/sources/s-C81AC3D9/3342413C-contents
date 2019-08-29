#script to randomly select additional coding to check reliability

#C3 has coded all papers from 1999-1999
#C1/C2 have coded half of the papers from 2000-2009 and have from 2010-now each
#So recoding is slightly asymmetrical to check especially for bias in coding of the first decade

#- C1 codes 2 MAs that C3 coded and 1 MA that C2 coded (3 in total)
#- C2 codes 2 MAs that C3 coded and 1 MA that C1 coded (3 in total) 
#- C3 codes 2 MAs that C2 coded (one from each decade) and 2 MAs that C1 coded (one from each decade) (4 in total)


#coder 1: = ST, coder 2: JP, coder 3 = EH

library(tidyverse)

ma_data = read.delim("forOSF/CodingSheet/CodingForm.txt", skip=1)
ma_data = ma_data %>%
  mutate(year = case_when(DoP >=1990 & DoP < 2000 ~ 1990,
                          DoP >=2000 & DoP < 2010 ~ 2000,
                          DoP >=2010 ~ 2010)) 


#Datasets that will be coded by C1
set.seed(521)
C1_from_C3 = ma_data %>%
  filter(Coder == 3) %>%
  sample_n(2)
set.seed(413)
C1_from_C2 = ma_data %>%
  filter(Coder == 2 & year == 2000) %>%
  sample_n(1)

C1_from_C3$Citation
#[1] Wood, W., Wong, F. Y., & Chachere, J. G. (1991). Effects of media violence on viewers' aggression in unconstrained social interaction. Psychological bulletin, 109(3), 371.                                              
#[2] Ito, T. A., Miller, N., & Pollock, V. E. (1996). Alcohol and aggression: A meta-analysis on the moderating effects of inhibitory cues, triggering events, and self-focused attention. Psychological Bulletin, 120(1), 60.
C1_from_C2$Citation
#[1] Grabe, S., Ward, L. M., & Hyde, J. S. (2008). The role of the media in body image concerns among women: a meta-analysis of experimental and correlational studies. Psychological bulletin, 134(3), 460.
#Datasets that will be coded by C2
set.seed(309)
C2_from_C3 = ma_data %>%
  filter(Coder == 3) %>%
  sample_n(2)
set.seed(201)
C2_from_C1 = ma_data %>%
  filter(Coder == 1 & year == 2010) %>%
  sample_n(1)

C2_from_C3$Citation
#[1] Eagly, A. H., Ashmore, R. D., Makhijani, M. G., & Longo, L. C. (1991). What is beautiful is good, but\xc9: A meta-analytic review of research on the physical attractiveness stereotype. Psychological bulletin, 110(1), 109.
#[2] A - Feingold, A. (1992). Good-looking people are not what we think. Psychological bulletin, 111(2), 304.  
C2_from_C1$Citation
#Mathewson, K. J., Chow, C. H., Dobson, K. G., Pope, E. I., Schmidt, L. A., & Van Lieshout, R. J. (2017). Mental health of extremely low birth weight survivors: A systematic review and meta-analysis. Psychological bulletin, 143(4), 347.

#Datasets that will be coded by C3
set.seed(103)
C3_from_C1_1 = ma_data %>%
  filter(Coder == 1 & year == 2000) %>%
  sample_n(1)
set.seed(756)
C3_from_C1_2 = ma_data %>%
  filter(Coder == 1 & year == 2010) %>%
  sample_n(1)
set.seed(888)
C3_from_C2_1 = ma_data %>%
  filter(Coder == 2 & year == 2000) %>%
  sample_n(1)
set.seed(900)
C3_from_C2_2 = ma_data %>%
  filter(Coder == 2 & year == 2010) %>%
  sample_n(1)

C3_from_C1_1$Citation
#[1] Gangestad, S. W., & Snyder, M. (2000). Self-monitoring: Appraisal and reappraisal. Psychological bulletin, 126(4), 530
C3_from_C1_2$Citation
#[1] Orquin, J. L., & Kurzban, R. (2016). A meta-analysis of blood glucose effects on human decision making. Psychological Bulletin, 142(5), 546.
C3_from_C2_1$Citation
#[1] Wood, W., & Quinn, J. M. (2003). Forewarned and forearmed? Two meta-analysis syntheses of forewarnings of influence appeals. Psychological Bulletin, 129(1), 119.
C3_from_C2_2$Citation
#[1] Harkin, B., Webb, T. L., Chang, B. P., Prestwich, A., Conner, M., Kellar, I., ... & Sheeran, P. (2016). Does monitoring goal progress promote goal attainment? A meta-analysis of the experimental evidence. Psychological bulletin, 142(2), 198.

