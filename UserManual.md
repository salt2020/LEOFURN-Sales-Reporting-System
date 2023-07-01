# Job Offer Comparison App User Manual
|Application   |  Job Offer Comparison App |
|---------------|----------------------------------|
|Utility | JAVA, Android Studio  |
|Release Date | 07/01/2023 |

# Table of contents
- [Main Menu](#MainMenu)  
- [Current Job](#CurrentJob)  
- [Enter Job Offers](#EnterJobOffers)
- [Comparison Settings](#ComparisonSettings)
- [Compare Jobs](#CompareJobs)  

### About this App <a name="AboutthisApp"></a>

This is a single-user job offer comparison app that allows you to enter job offers and compare the current job with job offers based on weights. 

### Main Menu <a name="MainMenu"></a>

To launch the app, tap the application icon on the screen of your Android device. And the main menu screen appears. 

<p align="center">
<img src="images/MainMenu.png" width="300"></p>
<p align="center">Figure 1. Main Menu Interface</p>

**Note:** Your screens might look somewhat different from the examples in this document, but the
basic elements are the same. 

There are four functions for you to operate. 

- [Current Job](#CurrentJob)
- [Enter Job Offers](#EnterJobOffers)
- [Comparison Settings](#ComparisonSettings)
- [Compare Jobs](#CompareJobs)  

### Current Job <a name="CurrentJob"></a>
If you want to enter (if it is the first time) or edit all of the details of your current job, click on the `CURRENT JOB` button and you will be redirect to the current job interface.
<p align="center">
<img src="images/CurrentJob.png" width="300"></p>
<p align="center">Figure 2. Current Job Interface</p>

In this interface, you can enter the following details: 
1. Title
2. Company
3. Location (entered as city and state)
4. Overall cost of living in the location 
5. Yearly salary (as USD)
6. Yearly bonus (as USD)
7. Leave days (number of whole days from 0 to 30 inclusive)
9. Maternity/Paternity Leave (number of whole days from 0 to 20 inclusive)
9. Life Insurance (Percentage of Salary as an integer: 0 - 10)

When you finish entering, click on the `SAVE` button to save your input. If you don't wish to save, click on the `BACK/CANCEL` button to exit and return to the main menu. 

### Enter Job Offers <a name="EnterJobOffers"></a>
If you want to enter the details of an job offer, click on `ENTER JOB OFFERS` button and you will be redirect to the enter job offers interface. 
<p align="center">
<img src="images/JobOffer.png" width="300"></p>
<p align="center">Figure 3. Job Offers Interface</p>

When you finish entering, click on the `SAVE` button to save your input. If you don't wish to save, click on the `BACK/CANCEL` button to exit and return to the main menu. 
You can choose to enter another offer by clicking on the `ENTER NEW JOB OFFERS` button again. 

### Comparison Settings <a name="ComparisonSettings"></a>
When you compare jobs in the list, you can assign weights to five details with default value 1 for all: 
* Yearly salary
* Yearly bonus
* Leave days
* Maternity/Paternity Leave
* Life Insurance

Click on the `JOB COMPARISON SETTINGS` button and you will be redirect to the comparison settings interface. 
<p align="center">
<img src="images/ComparisonSetting.png" width="300"></p>
<p align="center">Figure 4. Comparison Settings Interface</p>

You can enter **integer** weights. When you finish entering, click on the `SAVE` button to save your input. If you don't wish to save, click on the `BACK/CANCEL` button to exit and return to the main menu. 

### Compare Jobs <a name="CompareJobs"></a>
You can enter the compare jobs interface by clicking on the `COMPARE JOB OFFERS` button in the main menu. \

In this interface, you can see the list of job offers you have saved, displayed as Title and Company, including the current job (if you have saved and will be marked by "current").

<p align="center">
<img src="img/jobRankingCombine.png" width="620"></p>
<p align="center">Figure 5. Compare Jobs Interface (left) and two jobs are selected for further comparison (right) </p>

These jobs are ranked from best to worst by using a job score, which is computed as the weighted sum of: 
**`AYS + AYB + (LT * AYS / 260) + (MPL * AYS / 260) + (LI/100 * AYS)`**

where: 

```
AYS = yearly salary adjusted for cost of living
AYB = yearly bonus adjusted for cost of living
LT = Leave
MPL = Maternity/Paternity Leave
LI = Life Insurance

```


For example, if the weights are `3` for the `yearly salary`, `2` for the `Maternity/Paternity Leave`, and `1` for all other factors, the score would be computed as:\
`(3/8 * AYS) + (1/8 * AYB) + (1/8 * LT * AYS / 260) + (2/8 * MPL * AYS / 260) + (1/8* LI/100 * AYS)`

If you wish to compare two jobs in details, check the boxes on the right (Figure 5 right), and click on the `COMPARE OFFERS` button at the bottom of the Compare Jobs Interface. You will be directed to the Compare Two Jobs Interface. 

<p align="center">
<img src="img/twoJobs.png" width="300"></p>
<p align="center">Figure 6. Compare Two Jobs Interface</p>

In this compare two jobs interface, you will be shown a table comparing the two jobs displaying all the details for each job. If you wish to perform another comparison, click `back` and reselect two new jobs. 
