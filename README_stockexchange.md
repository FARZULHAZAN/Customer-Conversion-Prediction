# projects
Problem statement: From given xml file predict the quality of the question using ML models

Data Extraction:Data has been extracted from the xml file and made a dataframe after that just droped nill values 

Data Exploration: Drop unwanted columns like                'LastEditorDisplayName',
                                                            'ClosedDate',
                                                            'OwnerDisplayName',
                                                            'LastEditorUserId',
       									'AcceptedAnswerId',
										'CommunityOwnedDate',
										'ParentId',
										'CommunityOwnedDate',
										'OwnerUserId',
 										'PostTypeId',
										'LastActivityDate',
										'LastEditDate',
										'CreationDate'

because it wont help to decide the quality of the question.Final Dataframe will be having the columns of Id,Score,ViewCount,Body,Title,Tags,AnswerCount,CommentCount,FavoriteCount but Score and AnswerCount made as a one column as Quality (0,1,2) for very low,low,Good qualities respectively (Y for the model). 
And also change the datatypes for respective columns like for ID,CommentCount,FavoriteCount as int rest will be object .
Using BeautifulSoup package removed unwanted html tags from the Body column and find length of Body and made it as a feature.Same done for Tags and Title find its length and made it as feature for the problem.
file Dataframe now become full of integer values and try to find the outliers in each columns

1->For View Count Standard Deviation is more than the mean so there data is spread all over so no outliers in Viewcount.
2->For CommentCount Standard Deviation is more than the mean so there data is spread all over so no outliers in CommentCount.
3->For FavoriteCount Standard Deviation is more than the mean so there data is spread all over so no outliers in FavoriteCount.
4->For Title_length mean>std so will have the outliers so first plot the normal distribution curve for the title_length and made upperlimit as mean length +(3*std of the length) and lowerlimit as mean length -(3*std of the length) then removed the outlier of 639 values which is less than 1% of the total values so it wont affect much in the modeling.
5->For Tags_length mean>std so will have the outliers so first plot the normal distribution curve for the tags_length and made upperlimit as mean length +(3*std of the length) and lowerlimit as mean length -(3*std of the length) then removed the outlier of 1 value which is less than 1% of the total values so it wont affect much in the modeling.
6->For Body_length mean>std so will have the outliers so first plot the normal distribution curve for the Body_length and made upperlimit as mean length +(3*std of the length) and lowerlimit as mean length -(3*std of the length) then removed the outlier of 967 values which is less than 1% of the total values so it wont affect much in the modeling.

Modelling:Performed various models like logisticRegression,RandomforestClassifier,XGBclassifier,MultinomialNB outof which RandomForestClassifier very well with 83% accuracy score. least is MultinomialNB with 63%
