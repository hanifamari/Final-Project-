# Final-Project-Hotel AirBnB Price Prediction

Final Project Job Connector Data Science Jakarta Batch 9 Purwadhika, Hanif M Amari

## Busines Problem
- Sebagai seorang pengusaha yang ingin membuat bisnis perhotelan, faktor apakah yang paling menentukan harga hotel di New York?
- Area mana di New York yang paling banyak listing hotelnya dan mengapa banyak di daerah tersebut?
- Jenis room_type apa yang paling mahal dan mengapa?

## Dataset

    id : listing ID
    name : name of the listing
    host_id : host ID
    host_name : name of the host                     
    neighbourhood_group : location            
    neighbourhood : area                
    latitude : latitude coordinates                     
    longitude : longitude coordinates                      
    room_type : listing space type                     
    price : price in dollars                       
    minimum_nights : amount of nights minimum                
    number_of_reviews : number of reviews               
    last_review : latest review                  
    reviews_per_month : number of reviews per month              
    calculated_host_listings_count : amount of listing per host 
    availability_365 : number of days when listing is available for booking     
    
https://www.kaggle.com/dgomonov/new-york-city-airbnb-open-data?select=AB_NYC_2019.csv

## Step
Ada 3 langkah yang saya lakukan dalam dataset ini yaitu
- Data Cleansing (Checking null-value and duplicated row)
- Exploratory Data Analysis
- Machine Learning Modelling

### Data Cleansing
Terdapat null value di kolom `reviews_per_month`, `last_review`, `host_name`, `name`. Null value di kolom `reviews_per_month`, `last_review` memiliki letak dan posisi yang sama. Kemudian saya cek dibagian `number_of_reviews`. Ternyata semua `number_of_reviews` yang nilainya 0, `reviews_per_month`, `last_review` nilainya jadi null. Artinya null di kedua kolom ini bisa diimpute dengan 0. Sisanya tidak dapat diimpute dengan apapun jadi saya biarkan terlebih dahulu. Kemudian saya cek duplicate row baik yang complete maupun incomplete. Setelah dicek ternyata data sudah tidak ada duplicate 

### Exploratory Data Analysis
Mencari insight penting dari data berupa business insight ataupun kondisi data sebelum memasuki pemodelan machine learning

### Machine Learning Model
Sebelum pemodelan ada beberapa hal yang perlu dilakukan :
1. Handling outlier pada dependant varible
2. Feature selection untuk menentukan independent variable
3. Menentukan model dengan regression model
4. Evaluasi model

Model machine learning yang paling bagus adalah RandomForestRegressor dengan nilai
- RMSE Traning     = 46.956576
- RMSE Test        = 47.608812	
- R2_Score Test    = 0.524886
- R2_Score Traning = 0.513424

## Dashboard
Saya mengguanakan Flask untuk membuat dashboard

**Home**

![Capture](https://user-images.githubusercontent.com/60425527/92688272-47ccb300-f367-11ea-80de-e4d00dc84d64.PNG)

**Dataset**

![Capture](https://user-images.githubusercontent.com/60425527/92708097-0eed0800-f380-11ea-8f25-4f45beda905e.PNG)

**Exploratory Data Analysis**

![Capture](https://user-images.githubusercontent.com/60425527/92708552-68edcd80-f380-11ea-95e6-e3de99686793.PNG)

**Prediction**

![Capture](https://user-images.githubusercontent.com/60425527/92708805-99ce0280-f380-11ea-80dd-8db0e4a31ead.PNG)

**Machine Learning Prediction**

![Capture](https://user-images.githubusercontent.com/60425527/92709138-dc8fda80-f380-11ea-9be1-1cfcdc26fd2a.PNG)
