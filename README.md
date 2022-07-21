<img src="movieIntro.png">
# The Art of the Blockbuster

**Author:** Jake Sherman
***

## Overview

While many typical Hollywood hits tend to be rather formulaic, producing the next big movie is anything but.  The problem with producing movies is the unpredictable nature of their profitability.  This notebook a analyzes production budget, genre, and film runtime to see if the art of the blockbuster is really more of a science. 

Findings show that low budget movies have the highest ROI on average, mystery is the most profitable genre, and a runtime of 75-85 minutes will bring the most bang for your buck.

## Business Problem

Producing a movie is extremely capital intensive and unlike traditional investments, a movie can bomb and leave investors with a total loss of investment in the blink of an eye.  There is extremely high volatility in performance relative to other investments, often times movies are hit or miss.  This analysis aims to look at data, specifically relating to runtime, production budget, and film genre to see if there are ways a production company can focus its business plan to optimize profitability.

## Data Understanding

Data being used comes from a csv database containing information related to production budget and worldwide gross to determine the films ROI.  This dataframe was merged with a SQL database containing runtime and genre information. The target variable is ROI or return on investment which is calculated as ((worldwide theatrical gross / production budget)*100). The analysis looks at how ROI is affected by changes in runtime, genre, and production budget.

Alternatively, another dataframe was created that contained only data from films that were considered a 'success' by this analysis.  The requirement for 'success' was if a film returned double its production budget or achieved an ROI of 100%.  This method is more focused on reliability of performance and reduces emphasis on outlier returns.

## Data Preparation

The IMDB SQLdatabase only contains information on films dating back to 2010 so all films prior to 2010 were dropped in order to conduct the genre and runtime analysis. Entries with no runtime or genre were also dropped.

Film festivals also only recognize an entry as a feature film if it is at least 75 minutes long so all entries shorter were dropped.

Each film was associated with up to three genres.  One hot encoding is used to recognize these values for each film.

ROI column was added to the dataframe.

The study of production budget added back movies prior to 2010 as their runtime and genre were not required. However, some movies were self produced by film makers and/or had celebrity favors that allowed for a lower production budget than would otherwise be required- all entries below $500k production budget were dropped.

Although production budgets have a strong correlation to worldwide gross, there is no positive correlation to ROI.  As such production budgets were broken down into 4 tiers recognized in the industry:
        Low Budget Films: $0.5M-$5M
        Mid-Level Budget Films: $5M-$50M
        Big Budget Films: $50M-$100M
        Blockbuster Films: $100M+
Each tier is analyzed against ROI to determine the optimal production budget tier.

## Evaluation: Production Budget
The lowest budget tier has the highest average ROI and lowest median ROI.

Low budget movies are inherently riskier than larger movies as their median return is only 110% but they also tend to offer the largest upside as hits really skew the average ROI up.  The safest investment is the blockbuster budget tier where the average returns aren't the best but the median value is the highest suggesting less volatility and a safer floor.  Blockbuster tier movies have the lowest ROI standard deviation while low budget films have the highest.

Despite the decreased volatility of blockbuster tier movies, the average ROI stat disparity cannot be ignored and Microsoft's business model would be best served producing a plethora of low budgets films and playings the odds for making a hit movie to maximize their investment return.

# Conclusion
Assuming the investment object for Microsoft is to start a movie studio that will produce a slate of movies (not just a single film), they should focus their investment to a specific niche of movies that will maximize ROI.  While there is a direct correlation between production budget and worldwide gross, it is the low budget movies ($.5M - $5m) that prove to be the most profitable by a significant margin.  The mystery genre has the highest average  and median ROI which demostrates its superior upside and bankability relative to other genres.  The shortest films, 75-85 minutes, also returned the highest ROI, likely due in part to the correlation with production budget.

Low budget movies have the highest expected average return on investment.
Production budget has a large correlation to worldwide theatrical gross.
Shorter runtime films are the most profitable.
The mystery genre has the strongest profitability metrics.
Microsoft needs to focus on low budget mystery films to maximize ROI.
