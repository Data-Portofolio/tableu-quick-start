 <h1 align="center">
     <img src="https://github.com/Data-Portofolio/tableu-quick-start/assets/133883292/e52a1f2f-16e0-4cd2-907b-a388b916a4af" alt="Image" width="200" height="auto"/>
    <br>
    tableu</h1>

![image](https://github.com/Data-Portofolio/tableu-quick-start/assets/133883292/5ff5eebb-84ad-4d17-8c01-acbca4c42a9d)

## <img src="https://github.com/Data-Portofolio/tableu-quick-start/assets/133883292/44e0968e-345b-4008-981d-25508ef215d5" width="21" height="25"> 5 Steps to Analysis using Tableau

In Tableau, conducting an analysis typically involves several key steps:

1. **Data Check**: Before diving into analysis, ensure that your data is clean, accurate, and properly structured. This may involve checking for missing values, outliers, and inconsistencies. Tableau provides tools for data preparation and cleansing to streamline this process.

2. **Explore Data**: Once your data is in good shape, start exploring it in Tableau. This involves visually examining the data to identify patterns, trends, and relationships. Tableau's drag-and-drop interface allows for intuitive exploration of data by creating various visualizations like scatter plots, bar charts, and histograms.

3. **Analyze & Visualize Data**: After gaining insights from data exploration, move on to more in-depth analysis and visualization. Use Tableau's powerful features like calculated fields, filters, and parameters to perform complex analyses and create informative visualizations. This step often involves creating multiple charts, graphs, or maps to answer specific questions or test hypotheses.

4. **Dashboarding**: Once individual visualizations are created, assemble them into interactive dashboards in Tableau. Dashboards allow you to combine multiple views into a single interface, enabling users to interactively explore different aspects of the data. Customize the layout, add interactivity, and design visually appealing dashboards to effectively communicate insights.

5. **Communicate the Insights**: Finally, share your findings and insights with stakeholders or decision-makers. Use Tableau's storytelling capabilities to create compelling narratives around your data. Incorporate annotations, captions, and explanations to guide viewers through the analysis process and highlight key takeaways. Tableau also allows you to publish your dashboards to Tableau Server or Tableau Public for easy sharing and collaboration.

By following these steps, you can effectively analyze data using Tableau and communicate meaningful insights to drive informed decision-making.

## Parameter

### Time Block

```sql
IF DATEPART('hour', [Start Time]) >= 0 AND DATEPART('hour', [Start Time]) < 6 
    THEN 'Night'
ELSEIF DATEPART('hour', [Start Time]) >= 6 AND DATEPART('hour', [Start Time]) < 12
    THEN 'Morning'
ELSEIF DATEPART('hour', [Start Time]) >= 12 AND DATEPART('hour', [Start Time]) < 18
    THEN 'Afternoon'
ELSE 
    'Evening'
END
```

###  weekend or weekdays

```sql
IF DATEPART('day', [Start Time])=1 
    or DATEPART('day', [Start Time])= 7
THEN 'Weekend'
ELSE 'Weekday'
END
```

### Season

```sql
IF  datepart('month', [Start Time])<3 THEN 'Winter'
ELSEIF  datepart('month', [Start Time])<5 THEN 'Spring'
ELSE 'Summer'
END
```

### Trip Duration (hour)

```sql
DATEDIFF('hour', [Start Time], [End Time])
```


## Function in Tableu

### Aggregate Functions:
1. **SUM()**: Calculates the sum of a numerical field.
   Example: `SUM([Sales])`

2. **AVG()**: Calculates the average of a numerical field.
   Example: `AVG([Profit])`

3. **MIN()**: Finds the minimum value in a field.
   Example: `MIN([Order Date])`

4. **MAX()**: Finds the maximum value in a field.
   Example: `MAX([Sales])`

5. **COUNT()**: Counts the number of rows with non-null values in a field.
   Example: `COUNT([Customer ID])`

<details><summary>
🎯More explanation below</summary>
 
### Date Functions:
1. **DATEADD()**: Adds a specified interval to a date.
   Example: `DATEADD('year', 1, [Order Date])` adds one year to the Order Date.

2. **DATEDIFF()**: Calculates the difference between two dates.
   Example: `DATEDIFF('day', [Start Date], [End Date])` calculates the number of days between two dates.

3. **DATETRUNC()**: Truncates a date to a specified level of precision.
   Example: `DATETRUNC('quarter', [Order Date])` truncates the Order Date to the nearest quarter.

4. **DATEPART()**: Extracts a part of a date.
   Example: `DATEPART('month', [Order Date])` extracts the month from the Order Date.

5. **NOW()**: Returns the current date and time.
   Example: `NOW()` returns the current date and time.

6. **TODAY()**: Returns the current date.
   Example: `TODAY()` returns the current date without the time component.

7. **DATE()**: Creates a date from separate year, month, and day components.
   Example: `DATE(2022, 10, 15)` creates the date October 15, 2022.

8. **DATEPARSE()**: Parses a string into a date using a specified format.
   Example: `DATEPARSE('yyyy-MM-dd', '2022-10-15')` parses the string '2022-10-15' into a date.
    
### String Functions:
1. **LEFT()**: Returns the leftmost characters of a string.
   Example: `LEFT([Product Name], 5)` returns the first 5 characters of the Product Name.

2. **RIGHT()**: Returns the rightmost characters of a string.
   Example: `RIGHT([Customer Name], 3)` returns the last 3 characters of the Customer Name.

3. **MID()**: Returns a substring from within a string.
   Example: `MID([Description], 1, 10)` returns a substring of 10 characters starting from the 1st character of the Description.

4. **LEN()**: Returns the length of a string.
   Example: `LEN([Product Name])` returns the number of characters in the Product Name.

5. **UPPER()**: Converts a string to uppercase.
   Example: `UPPER([City])` converts the City name to uppercase.

6. **LOWER()**: Converts a string to lowercase.
   Example: `LOWER([Country])` converts the Country name to lowercase.

7. **TRIM()**: Removes leading and trailing spaces from a string.
   Example: `TRIM([Description])` removes leading and trailing spaces from the Description.

8. **REPLACE()**: Replaces occurrences of a substring within a string with another substring.
   Example: `REPLACE([Product Name], 'Chair', 'Table')` replaces 'Chair' with 'Table' in the Product Name.

9. **CONTAINS()**: Checks if a string contains another substring.
   Example: `CONTAINS('Hello, World!', 'World')` returns TRUE if 'Hello, World!' contains 'World'.

10. **FIND()**: Returns the position of a substring within a string.
    Example: `FIND('cat', 'The cat is on the mat')` returns 5 as 'cat' starts at the 5th position in the string.

11. **SPLIT()**: Splits a string into an array of substrings based on a delimiter.
    Example: `SPLIT('apple,orange,banana', ',')` returns an array containing 'apple', 'orange', and 'banana'.

12. **STR()**: Converts a value to a string.
    Example: `STR([Sales])` converts the Sales value to a string.

Certainly! Here are some logical functions in Tableau along with examples of their usage:

### Logical Functions:
1. **IF-THEN-ELSE**: Conditional statement that returns different results based on a condition.
   Example: `IF [Sales] > 1000 THEN 'High' ELSE 'Low' END` categorizes sales as 'High' if greater than 1000, otherwise 'Low'.

2. **CASE**: Conditional statement that evaluates multiple conditions.
   Example: 
   ```sql
   CASE 
       WHEN [Category] = 'Furniture' THEN 'Office Furniture'
       WHEN [Category] = 'Technology' THEN 'Electronics'
       ELSE 'Other' 
   END
   ```
   
3. **AND**: Logical AND operation.
    example:
    ```
    IF [Sales] > 1000 AND [Profit] > 500
    THEN 'High Profit' ELSE 'Low Profit'
    END` checks if both sales and profit are above certain thresholds.
    ```
5. **OR**: Logical OR operation.
   Example:
   ```
   IF [Region] = 'North' OR [Region] = 'South'
   THEN 'Northern or Southern Region' ELSE 'Other Regions'
   END` checks if the region is either 'North' or 'South'.
   ```
7. **NOT**: Logical NOT operation.
   Example:
   ```
   IF NOT ISNULL([Discount])
   THEN 'Discount Applied'
   ELSE 'No Discount Applied'
   END` checks if the discount field is not null.
   ```
These logical functions in Tableau are essential for implementing conditional logic in your data analysis. They allow you to control how your data is categorized, filtered, or displayed based on specific conditions.

### Number Functions:
1. **ABS()**: Returns the absolute value of a number.
   Example: `ABS([Profit])`

2. **ROUND()**: Rounds a number to a specified number of decimal places.
   Example: `ROUND([Discount], 2)`

### Table Calculation Functions:
1. **WINDOW_SUM()**: Calculates a running sum of a field within a specified window.
   Example: `WINDOW_SUM(SUM([Sales]))`

2. **RUNNING_SUM()**: Calculates a running sum of a field.
   Example: `RUNNING_SUM([Profit])`

### Type Conversion Functions:
1. **INT()**: Converts a value to an integer.
   Example: `INT([Quantity])`

2. **STR()**: Converts a value to a string.
   Example: `STR([Sales])`

### Statistical Functions:
1. **ZN()**: Replaces null values with zero.
   Example: `ZN([Sales])`

2. **NULLIF()**: Returns null if two expressions are equal.
   Example: `NULLIF([Profit], 0)`

Certainly! Here are some geographic functions in Tableau along with examples of their usage:

### Geographic Functions:
1. **MAKEPOINT()**: Creates a point geometry from latitude and longitude values.
   Example: `MAKEPOINT([Latitude], [Longitude])`

2. **DISTANCE()**: Calculates the distance between two points.
   Example: `DISTANCE([Origin], [Destination])`

3. **AREA()**: Calculates the area of a polygon.
   Example: `AREA([Polygon])`

4. **BUFFER()**: Creates a buffer zone around a point, line, or polygon.
   Example: `BUFFER([Location], 10, 'kilometers')`

5. **CONTAINS()**: Checks if one geometry contains another.
   Example: `CONTAINS([Polygon], [Point])`

6. **INTERSECTS()**: Checks if two geometries intersect.
   Example: `INTERSECTS([Polygon1], [Polygon2])`

7. **WITHIN()**: Checks if one geometry is within another.
   Example: `WITHIN([Point], [Polygon])`

These geographic functions are useful for spatial analysis and creating geospatial visualizations in Tableau. They allow you to perform operations such as calculating distances between locations, determining containment relationships, and creating buffer zones around points of interest.
</details>

## Group
### Group
- `Group` adalah penggabungan baris terkait dalam sebuah kolom.
  
  >**Contohnya**: dalam dataset negara di seluruh dunia, kita bisa mengelompokkan baris-baris ini menjadi benua berdasarkan nama negaranya.
  
- Ada dua kasus penggunaan utama untuk `Group`:
  - untuk menciptakan konsistensi dalam data, seperti menggabungkan penulisan yang berbeda untuk hal yang sama.
  - untuk memberikan tingkat agregasi baru, seperti mengelompokkan produk-produk ke dalam kategori-kategori seperti aksesori, perabotan, pakaian, dll.

### Parameter
- Parameters dalam Tableau adalah nilai penampung global seperti angka, tanggal, atau string yang dapat menggantikan nilai konstan dalam suatu perhitungan, filter, atau garis referensi. Ini memungkinkan Anda untuk menyampaikan nilai ke visualisasi Anda untuk secara dinamis mengubah apa yang ditampilkan.

  > Misalnya, mengubah tampilan dari 15 stasiun teratas menjadi 50 stasiun teratas. Kunci dari sebuah parameter adalah kemampuannya untuk mengirimkan nilai ke lembar      kerja menggunakan Pengendali Parameter. Ini akan menjadi jelas dalam latihan berikutnya ketika kita membuat Parameter dan mengaitkannya dengan sebuah Bidang.Hitung  dan filter. Setelah dibuat, Anda akan melihat bahwa Parameters berada di bagian tersendiri dalam panel Data. Mari kita lihat beberapa contoh.

<details><summary>Example: </summary>
 <br>
 
![image](https://github.com/Data-Portofolio/tableu-quick-start/assets/133883292/ec3ff6d0-1730-49f5-a326-4379eacd1aac)
</details>

### Set

- Set dalam Tableau adalah kumpulan data yang dibuat untuk mengelompokkan nilai-nilai tertentu dalam satu kelompok. Setiap nilai dalam set bisa menjadi bagian dari set ("IN") atau di luar set ("OUT"). Anda dapat membuat set berdasarkan kondisi tertentu, seperti nilai-nilai yang memenuhi kriteria tertentu atau nilai-nilai yang dipilih secara manual.

  > Contoh penggunaan set dalam Tableau termasuk pembagian data menjadi kategori-kategori tertentu untuk analisis lebih lanjut, atau membandingkan kinerja anggota set     dengan anggota di luar set. Set dapat digunakan dalam perhitungan, filter, dan visualisasi untuk membantu dalam pemodelan data dan analisis.
