This project attempts to determine why a driver might accept a coupon that appears on their cellphone. 
Main question: What factors (personal or environmental) might increase the odds of a cell phone coupon being accepted?
Answering this question is useful to advertisers since it increases the success rate of the coupon campaign. It is also useful to cellphone owners since it increases the chance they'll receive a coupon that they want!

The dataset is sourced from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk:
https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation

It consists of 12_684 rows and 26 columns related to the data collected in the survey.

Paul Butcher maintains and contributes to this project as a starter for his AI course with UC Berkeley.

Results
The coupon campaign was relatively successful with 56.8% of the coupons accepted overall. There were five types of coupons offered with their success rates shown in the histogram below
<img width="395" height="355" alt="output_14_0" src="https://github.com/user-attachments/assets/cbce3b09-29b9-419a-9060-c61caafd675e" />

Bar Coupons

Bottom line up front: the highest bar coupon acceptance rate (72.2%) was for respondents between 26 and 30 who attend bars at least monthly.

The coupons for bar offers were considered in detail by focussing on the subset of data where 2017 bar coupons were received. 827 of these coupons were accepted, representing an acceptance rate of 41.0%. Those bar coupon recipients who reported attending bars 4 or more times per month had a coupon acceptance rate of 81.5%. This stands in contrast to the rest with an acceptance rate of 18.5%. Clearly targeting regular bar attendees will lead to a highly successful campaign for bar coupons.
What about other factors for bar coupons? 
Of the 504 respondents too young to drink, 247 still accepted them! Whether these actions were aspirational or not is hard to determine. It is hard to condone targeting this age bracket, despite the apparent success rate. For those over 25, the bar coupon acceptance rate was only 28.8%. Most of these respondents don't regularly attend bars, however. Looking at those that do (at least monthly) and are over 25 returned a bar coupon success rate of 69.5%. Moreover, if under 30, the acceptance rate rose to 72.2% and represents a market segment worth targeting.
Other segements:
If drivers had passengers with them (not kids), the rate dropped to 48.4%
Those regularly dining at cheap restaurants returned a 42% bar coupon acceptance rate.

Coffee Coupons
3996 coffee house coupons were received by respondents in the survey. 49.9% were accepted - a higher rate than the bar coupons.
The most significant finding in analysing coffee coupon data was that 62.8% of those accepting coffee house coupons were non-urgent travellers. Those heading to work or home were generally less interested in stopping.

Data Cleaning
Nulls required attention in the dataset as can be seen as blue bars in the image below.  The right-most 'car' column has a large number of nulls and so do some of the other columns. 

<img width="402" height="383" alt="output_8_1" src="https://github.com/user-attachments/assets/0674b022-dc0a-4f5e-886a-d5f6493ac51a" />

A closer inspection of the 'cars' column revealed 108 rows with valid data or 0.85% of the 12k+ rows. This data is not especially revealing and does not add value. So  the column was dropped from further consideration.
Other nulls were also present and these were dealt with by replacement with integer 0. The removal of all nulls was confirmed by a bar plot of nulls across the whole dataset:

<img width="400" height="383" alt="output_10_2" src="https://github.com/user-attachments/assets/a98f1f63-5a29-4bc1-b500-f67f7524d78b" />

Several columns contained strings "less1" and "never". These were also converted to integer 0.



