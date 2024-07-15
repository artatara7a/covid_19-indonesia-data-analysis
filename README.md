<p align="center" style="font-size: 25px; font-weight: bolder;">Covid-19 Indonesia Data Analysis</p>

## 🧰 Tools
- Python
- SQL
- Pandas
- Numpy
- Plotly
- Matplotlib
- HTML
- CSS

## 🗂️ Documentation
1. Pre-processing
    - Transforming

        Used to change the data type in the 'Date' column
        ```
        data['Date'] = data['Date'].map(parser.parse)
        data.info()
        ```
        
    - Cleansing

        Used for Analysis of Indonesian Covid Cases by Year
        ```
        analisis_1 = data.dropna(subset=['Island'])
        analisis_1 = analisis_1.select_dtypes(exclude=['object'])
        
        columns_to_keep = list(analisis_1.columns[:5]) + list(analisis_1.columns[-2:])
        
        analisis_1 = analisis_1[columns_to_keep]
        analisis_1.info()
        ```
        
        Used for Analysis of Indonesian Covid Cases by Island
        ```
        analisis_2 = data.dropna(subset=['Island'])
        analisis_2 = analisis_2.select_dtypes(exclude=['object']) 
        
        columns_to_keep = list(analisis_2.columns[np.r_[1:5, 15:23]]) + list(analisis_2.columns[-2:])
        
        analisis_2 = analisis_2[columns_to_keep]
        analisis_2 = analisis_2.drop(columns=["Longitude", "Latitude", "Total Cases per Million"])
        analisis_2 = analisis_2.join(data["Island"])
        analisis_2.info()
        ```

        Used for Analysis of Indonesian Covid Cases by Island and Year
        ```
        analisis_3 = data.dropna(subset=['Island'])
        analisis_3 = analisis_3.select_dtypes(exclude=['object']) 	
        analisis_3 = analisis_3.drop(columns=["City or Regency", "Total Regencies", "Total Cities", "Total Districts", 
                                            "Total Urban Villages", "Total Rural Villages", "Longitude", "Latitude"])
        analisis_3 = analisis_3.join(data["Island"])
        analisis_3.info()
        ```

    
2. Processing (Result)
    
    - Analysis of Indonesian Covid Cases by Year        
        <img src='![docs\newplot.png](https://raw.githubusercontent.com/artatara7a/covid_19-indonesia-data-analysis/master/docs/newplot.png.png)' alt="Gambar" width="100%"/>
                
    - Analysis of Indonesian Covid Cases by Island          
        <img src="![docs\newplot2.png](https://raw.githubusercontent.com/artatara7a/covid_19-indonesia-data-analysis/master/docs/newplot2.png.png)" alt="Gambar" width="100%"/>

    - Analysis of Indonesian Covid Cases by Island and Year
        ![Gambar](https://raw.githubusercontent.com/artatara7a/covid_19-indonesia-data-analysis/master/docs/newplot3.png.png)

    - Other Analysis
        ![Gambar](https://raw.githubusercontent.com/artatara7a/covid_19-indonesia-data-analysis/master/docs/g_11.png)