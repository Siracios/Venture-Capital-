```python
"""First we import al the datasets and cleand the duplicates"""
import pandas as pd
COM = pd.read_excel('2223MBD41_Project_Dataset-v01.xlsx',sheet_name= 'COMPANY')
INV = pd.read_excel('2223MBD41_Project_Dataset-v01.xlsx',sheet_name= 'INVESTMENT')
ACQ = pd.read_excel('2223MBD41_Project_Dataset-v01.xlsx',sheet_name= 'ACQUISITION')
EMP = pd.read_excel('2223MBD41_Project_Dataset-v01.xlsx',sheet_name= 'EMPLOYEE')
COM.drop_duplicates()
INV.drop_duplicates()
ACQ.drop_duplicates()
EMP.drop_duplicates()

```





  <div id="df-f8467d27-672a-4386-a3d2-97fc5dc17d8b">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>EMPLOYEE_MD5</th>
      <th>JOB_TITLES</th>
      <th>COMPANY_NAME</th>
      <th>ATTENDED_SCHOOLS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>aac4a9fe0edc50a77072eae64578a892</td>
      <td>CEO</td>
      <td>Twitter</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>f9c87bcba2ffe2237e039b2e2c86b16f</td>
      <td>Co-Founder</td>
      <td>Twitter</td>
      <td>Northeastern University University of Massach...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>36830ffebad9a630da8a7a03a45f2730</td>
      <td>Team Member</td>
      <td>Twitter</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>84a91ad0f9b4149759f47fdc949fed42</td>
      <td>General Counsel</td>
      <td>Twitter</td>
      <td>Cornell University New York University School...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7881769fc62f54c36a687bda02b66198</td>
      <td>VP, Trust &amp; Safety</td>
      <td>Twitter</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>20697</th>
      <td>72c32150cb3f9b6e806fa530ed610175</td>
      <td>Chairman and CEO</td>
      <td>Iberdrola</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>20698</th>
      <td>dd0ae519effadbef7559d299ad355f1f</td>
      <td>Digital Channels Specialist Web Analyst</td>
      <td>Iberdrola</td>
      <td>EAE Business School</td>
    </tr>
    <tr>
      <th>20699</th>
      <td>aae97cfe2ea38ca0609a341e984b6b57</td>
      <td>CEO</td>
      <td>JD Logistics</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>20700</th>
      <td>b8a8c88bce6444121ebce4ef8d41a204</td>
      <td>Data Scientist</td>
      <td>Keywords Studios</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>20701</th>
      <td>c38442d6eaf4381a97379a05dc840f92</td>
      <td>CEO</td>
      <td>Citi</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>20702 rows × 4 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-f8467d27-672a-4386-a3d2-97fc5dc17d8b')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-f8467d27-672a-4386-a3d2-97fc5dc17d8b button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-f8467d27-672a-4386-a3d2-97fc5dc17d8b');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




# Sección nueva


```python
"""We check the first data set. Noticed all the data is not numeric.
1000 companies with 9 categories of revenu range and 10 categories of employee number """
COM.describe(include='all').T 
```





  <div id="df-df11a2a3-8aec-4be6-8707-c600c0ffaf17">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>unique</th>
      <th>top</th>
      <th>freq</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>COMPANY_NAME</th>
      <td>1000</td>
      <td>1000</td>
      <td>Twitter</td>
      <td>1</td>
    </tr>
    <tr>
      <th>CATEGORY</th>
      <td>1000</td>
      <td>977</td>
      <td>Biotechnology, Health Care, Medical, Pharmaceu...</td>
      <td>5</td>
    </tr>
    <tr>
      <th>LOCATION</th>
      <td>1000</td>
      <td>255</td>
      <td>San Francisco, California, United States</td>
      <td>173</td>
    </tr>
    <tr>
      <th>FOUNDED_ON</th>
      <td>1000</td>
      <td>428</td>
      <td>2012</td>
      <td>55</td>
    </tr>
    <tr>
      <th>EXITED_ON</th>
      <td>1000</td>
      <td>269</td>
      <td>—</td>
      <td>678</td>
    </tr>
    <tr>
      <th>CLOSED_ON</th>
      <td>1000</td>
      <td>6</td>
      <td>—</td>
      <td>995</td>
    </tr>
    <tr>
      <th>REVENU_RANGE</th>
      <td>1000</td>
      <td>9</td>
      <td>$1M to $10M</td>
      <td>230</td>
    </tr>
    <tr>
      <th>EMPLOYEE_NUMBER</th>
      <td>1000</td>
      <td>10</td>
      <td>101-250</td>
      <td>196</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-df11a2a3-8aec-4be6-8707-c600c0ffaf17')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-df11a2a3-8aec-4be6-8707-c600c0ffaf17 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-df11a2a3-8aec-4be6-8707-c600c0ffaf17');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""The distribution of the REVENU_RANGE concentrate almost 50% of the companies in the ranges $1M to $10M  and $10M to $50M  .
Only 4% of the sample are $10B+ . We notice also some cases with — ( No data)  """

COM['REVENU_RANGE'].value_counts(normalize=True)

```




    $1M to $10M       0.230
    $10M to $50M      0.216
    $100M to $500M    0.166
    $50M to $100M     0.103
    $1B to $10B       0.077
    Less than $1M     0.073
    $500M to $1B      0.047
    —                 0.046
    $10B+             0.042
    Name: REVENU_RANGE, dtype: float64




```python
"""The distribution of the EMPLOYEE_NUMBER concentrate almost 40% of the companies in the ranges 101-250  and 251-500 .
 We also notice also some cases with — ( No data)  """
COM['EMPLOYEE_NUMBER'].value_counts(normalize=True)
```




    101-250       0.196
    251-500       0.156
    1001-5000     0.155
    11-50         0.124
    501-1000      0.119
    51-100        0.095
    10001+        0.095
    5001-10000    0.033
    1-10          0.025
    —             0.002
    Name: EMPLOYEE_NUMBER, dtype: float64




```python
"""We check the first data set. Noticed all the data is not numeric.
5937 investment with 5 investment_stage and 28 categories of FUNDING_TYPE """
INV.describe(include='all').T 
```





  <div id="df-73cd409f-64b0-4c88-85c9-1250e0ad0d98">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>unique</th>
      <th>top</th>
      <th>freq</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>COMPANY_NAME</th>
      <td>5937</td>
      <td>935</td>
      <td>Tesla</td>
      <td>36</td>
    </tr>
    <tr>
      <th>FUNDING_TYPE</th>
      <td>5937</td>
      <td>28</td>
      <td>Series A</td>
      <td>854</td>
    </tr>
    <tr>
      <th>MONEY_RAISED</th>
      <td>5937</td>
      <td>1210</td>
      <td>—</td>
      <td>1028</td>
    </tr>
    <tr>
      <th>ANNOUNCED_DATE</th>
      <td>5937</td>
      <td>2331</td>
      <td>Dec 8, 2020</td>
      <td>25</td>
    </tr>
    <tr>
      <th>INVESTMENT_STAGE</th>
      <td>5937</td>
      <td>5</td>
      <td>—</td>
      <td>1766</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-73cd409f-64b0-4c88-85c9-1250e0ad0d98')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-73cd409f-64b0-4c88-85c9-1250e0ad0d98 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-73cd409f-64b0-4c88-85c9-1250e0ad0d98');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""The distribution of the INVESTMENT_STAGE concentrate almost 50% of the companies in the EARLY and Late stage Venture .
 We also notice the cases with  — ( No data) concentrate 29%. Low concentration for Seed and Pirvate Equity """
INV['INVESTMENT_STAGE'].value_counts(normalize=True)
```




    —                      0.297457
    Early Stage Venture    0.261917
    Late Stage Venture     0.251305
    Seed                   0.160687
    Private Equity         0.028634
    Name: INVESTMENT_STAGE, dtype: float64




```python
"""The objective is to transform de MONEY_RAISED into numeric data. First we delete al the null values """

INV2 = INV.loc[INV["MONEY_RAISED"] != "—"]
INV2.describe(include='all').T 

```





  <div id="df-8eb2d35a-6b9b-4f08-98bf-185f7434dcc8">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>unique</th>
      <th>top</th>
      <th>freq</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>COMPANY_NAME</th>
      <td>4909</td>
      <td>926</td>
      <td>Tesla</td>
      <td>35</td>
    </tr>
    <tr>
      <th>FUNDING_TYPE</th>
      <td>4909</td>
      <td>28</td>
      <td>Series A</td>
      <td>772</td>
    </tr>
    <tr>
      <th>MONEY_RAISED</th>
      <td>4909</td>
      <td>1209</td>
      <td>$10,000,000</td>
      <td>140</td>
    </tr>
    <tr>
      <th>ANNOUNCED_DATE</th>
      <td>4909</td>
      <td>2108</td>
      <td>Dec 10, 2020</td>
      <td>24</td>
    </tr>
    <tr>
      <th>INVESTMENT_STAGE</th>
      <td>4909</td>
      <td>5</td>
      <td>Early Stage Venture</td>
      <td>1434</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-8eb2d35a-6b9b-4f08-98bf-185f7434dcc8')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-8eb2d35a-6b9b-4f08-98bf-185f7434dcc8 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-8eb2d35a-6b9b-4f08-98bf-185f7434dcc8');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""The objective is to transform de MONEY_RAISED into numeric data. With the formula we transform
 to numbers and we transform all to USD  """

def GetDollar(x):
    if   x[0] == '€' :
       return(float(str(x[1:]).replace(",", ""))*1.06)
    elif x[0:3] == "CA$" :
       return(float(str(x[3:]).replace(",", ""))*0.74)
    elif x[0] == "¥" :
       return(float(str(x[1:]).replace(",", ""))*0.0075)
    elif x[0:2] == "R$" :
       return(float(str(x[2:]).replace(",", ""))*0.1895)
    elif x[0:3] == "CN¥" :
       return(float(str(x[3:]).replace(",", ""))*0.143676)
    elif x[0:3] == "ZAR" :
       return(float(str(x[3:]).replace(",", ""))*0.058)
    elif x[0:3] == "SGD" :
       return(float(str(x[3:]).replace(",", ""))*0.74)
    elif x[0:2] == "A$" :
       return(float(str(x[2:]).replace(",", ""))*0.67)
    elif x[0] == "₩" :
       return(float(str(x[1:]).replace(",", ""))*0.00079)
    elif x[0:3] == "CHF" :
       return(float(str(x[3:]).replace(",", ""))*1.8)
    elif x[0:3] == "MYR" :
       return(float(str(x[3:]).replace(",", ""))*0.23)
    elif x[0:3] == "RUB" :
       return(float(str(x[3:]).replace(",", ""))*0.014)
    elif x[0] == "₹" :
       return(float(str(x[1:]).replace(",", ""))*0.012)
    elif x[0:3] == "SEK" :
       return(float(str(x[3:]).replace(",", ""))*0.95)
    else:
      return(float(str(x[1:]).replace(",", "")))
  
```


```python
"""We create 'M_R_USD' to express the money raised in USD in a numeric form.
We notice de average amount of money raised was $133,805,088."""
INV2['M_R_USD'] = INV2['MONEY_RAISED'].apply(GetDollar).round()
INV2.describe(include='all').T 
```

    <ipython-input-8-fe964e064f73>:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      INV2['M_R_USD'] = INV2['MONEY_RAISED'].apply(GetDollar).round()






  <div id="df-2eef070d-7e49-4a3d-9583-b5320a25ce41">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>unique</th>
      <th>top</th>
      <th>freq</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>COMPANY_NAME</th>
      <td>4909</td>
      <td>926</td>
      <td>Tesla</td>
      <td>35</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>FUNDING_TYPE</th>
      <td>4909</td>
      <td>28</td>
      <td>Series A</td>
      <td>772</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>MONEY_RAISED</th>
      <td>4909</td>
      <td>1209</td>
      <td>$10,000,000</td>
      <td>140</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>ANNOUNCED_DATE</th>
      <td>4909</td>
      <td>2108</td>
      <td>Dec 10, 2020</td>
      <td>24</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>INVESTMENT_STAGE</th>
      <td>4909</td>
      <td>5</td>
      <td>Early Stage Venture</td>
      <td>1434</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>M_R_USD</th>
      <td>4909.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>133805088.28682</td>
      <td>522589158.53715</td>
      <td>6500.0</td>
      <td>4999998.0</td>
      <td>20000000.0</td>
      <td>75000000.0</td>
      <td>14000000000.0</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-2eef070d-7e49-4a3d-9583-b5320a25ce41')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-2eef070d-7e49-4a3d-9583-b5320a25ce41 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-2eef070d-7e49-4a3d-9583-b5320a25ce41');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""Here is the top 5 MONEY_RAISED ranking. Leading is ANT Group with colecting in it´s Series C $14,000,000,000"""

import numpy as np
INV3 = INV2.sort_values(['M_R_USD'],ascending=[False])
INV3.head()
```





  <div id="df-9edfcfd1-c3c3-4c19-86d6-3b0915ded429">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>COMPANY_NAME</th>
      <th>FUNDING_TYPE</th>
      <th>MONEY_RAISED</th>
      <th>ANNOUNCED_DATE</th>
      <th>INVESTMENT_STAGE</th>
      <th>M_R_USD</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5038</th>
      <td>Ant Group</td>
      <td>Series C</td>
      <td>$14,000,000,000</td>
      <td>Jun 8, 2018</td>
      <td>Late Stage Venture</td>
      <td>1.400000e+10</td>
    </tr>
    <tr>
      <th>3726</th>
      <td>Facebook</td>
      <td>Post-IPO Equity</td>
      <td>$13,787,117,488</td>
      <td>Oct 20, 2014</td>
      <td>—</td>
      <td>1.378712e+10</td>
    </tr>
    <tr>
      <th>5064</th>
      <td>BP</td>
      <td>Post-IPO Debt</td>
      <td>$12,000,000,000</td>
      <td>Jun 18, 2020</td>
      <td>—</td>
      <td>1.200000e+10</td>
    </tr>
    <tr>
      <th>153</th>
      <td>Meituan</td>
      <td>Post-IPO Equity</td>
      <td>$6,588,000,000</td>
      <td>Apr 19, 2021</td>
      <td>—</td>
      <td>6.588000e+09</td>
    </tr>
    <tr>
      <th>5739</th>
      <td>Sberbank</td>
      <td>Post-IPO Debt</td>
      <td>$5,800,000,000</td>
      <td>Jul 7, 2014</td>
      <td>—</td>
      <td>5.800000e+09</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-9edfcfd1-c3c3-4c19-86d6-3b0915ded429')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-9edfcfd1-c3c3-4c19-86d6-3b0915ded429 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-9edfcfd1-c3c3-4c19-86d6-3b0915ded429');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""Here is the top 10 of total MONEY_RAISED ranking. 
Leading is Reliance Jio Group with with a total of $2.444016e+10 colected in 15 rounds.
It interesting to see thath 50% of the ranking colected their total in 5 rounds or less"""
INV4 = INV2.groupby('COMPANY_NAME').agg({'M_R_USD': [np.sum, np.max, np.min, np.count_nonzero]})
INV5 = INV4.sort_values([('M_R_USD', 'sum')], ascending=False).head(10)
INV5
```





  <div id="df-38b1bb15-a2f2-452a-8dc0-3c4671853d66">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="4" halign="left">M_R_USD</th>
    </tr>
    <tr>
      <th></th>
      <th>sum</th>
      <th>amax</th>
      <th>amin</th>
      <th>count_nonzero</th>
    </tr>
    <tr>
      <th>COMPANY_NAME</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Reliance Jio</th>
      <td>2.444016e+10</td>
      <td>5.228880e+09</td>
      <td>8.760000e+07</td>
      <td>15</td>
    </tr>
    <tr>
      <th>Tesla</th>
      <td>2.298710e+10</td>
      <td>2.700000e+09</td>
      <td>7.500000e+06</td>
      <td>35</td>
    </tr>
    <tr>
      <th>Facebook</th>
      <td>1.950962e+10</td>
      <td>1.378712e+10</td>
      <td>1.500000e+07</td>
      <td>15</td>
    </tr>
    <tr>
      <th>Ant Group</th>
      <td>1.850000e+10</td>
      <td>1.400000e+10</td>
      <td>4.500000e+09</td>
      <td>2</td>
    </tr>
    <tr>
      <th>Meituan</th>
      <td>1.728800e+10</td>
      <td>6.588000e+09</td>
      <td>4.000000e+08</td>
      <td>5</td>
    </tr>
    <tr>
      <th>Uber</th>
      <td>1.721370e+10</td>
      <td>3.500000e+09</td>
      <td>2.000000e+05</td>
      <td>20</td>
    </tr>
    <tr>
      <th>Didi</th>
      <td>1.565080e+10</td>
      <td>5.500000e+09</td>
      <td>2.000000e+06</td>
      <td>15</td>
    </tr>
    <tr>
      <th>BP</th>
      <td>1.200000e+10</td>
      <td>1.200000e+10</td>
      <td>1.200000e+10</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Sberbank</th>
      <td>1.160000e+10</td>
      <td>5.800000e+09</td>
      <td>5.800000e+09</td>
      <td>2</td>
    </tr>
    <tr>
      <th>Siemens</th>
      <td>8.912900e+09</td>
      <td>4.452000e+09</td>
      <td>8.900000e+06</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-38b1bb15-a2f2-452a-8dc0-3c4671853d66')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-38b1bb15-a2f2-452a-8dc0-3c4671853d66 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-38b1bb15-a2f2-452a-8dc0-3c4671853d66');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""Here is a plot line the top 10 of total MONEY_RAISED and the max amount colected in one round. 
It interesting to see that in the top 3 the max amount is not relevant to the total amount colected.
Also interesting to see that in some cases of  the ranking the max amount is almost all the amount colected
There isn´t a strict correlation """
INV5[[('M_R_USD', 'sum'),('M_R_USD', 'amax')]].plot.line()
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f6cd3965670>




    
![png](output_12_1.png)
    



```python
"""In the flowwing plot scatter we compare the total amount raised with the number of funding stages.
Regardlees the company with most money raised is the company with highest investment rounds ,
We see there is not a clear correlation between this two variables. 
We see a lot of companies with high number of investment rounds and low total money raised, and viceversa.
 """

INV4.plot.scatter(x= [('M_R_USD', 'count_nonzero')], y = [('M_R_USD', 'sum')])
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f6cd3a765e0>




    
![png](output_13_1.png)
    



```python
"""If we group the M_R_USD by FUNDING_TYPE we notice the most frequent are SERIES A,B and C.
The top 3 of highest total colected are Post-IPO Equity,Post-IPO Debt and Private Equity.
Meanwhile the top 3 of higest average colected are Post-IPO Secondary,Post-IPO Debt and Post-IPO Equity.
 """

INV6 = INV2.groupby('FUNDING_TYPE').agg({'M_R_USD': [np.sum, np.mean, np.max, np.min, np.count_nonzero]})
INV6.sort_values([('M_R_USD', 'count_nonzero')], ascending=False)
```





  <div id="df-b08e4d2c-7993-48e0-8bec-c4f867dcc418">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="5" halign="left">M_R_USD</th>
    </tr>
    <tr>
      <th></th>
      <th>sum</th>
      <th>mean</th>
      <th>amax</th>
      <th>amin</th>
      <th>count_nonzero</th>
    </tr>
    <tr>
      <th>FUNDING_TYPE</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Series A</th>
      <td>2.137393e+10</td>
      <td>2.768644e+07</td>
      <td>2.054567e+09</td>
      <td>32000.0</td>
      <td>772</td>
    </tr>
    <tr>
      <th>Series B</th>
      <td>2.931778e+10</td>
      <td>4.428667e+07</td>
      <td>4.500000e+09</td>
      <td>673000.0</td>
      <td>662</td>
    </tr>
    <tr>
      <th>Series C</th>
      <td>5.365400e+10</td>
      <td>9.773043e+07</td>
      <td>1.400000e+10</td>
      <td>85000.0</td>
      <td>549</td>
    </tr>
    <tr>
      <th>Seed</th>
      <td>2.083618e+09</td>
      <td>3.872895e+06</td>
      <td>1.000000e+09</td>
      <td>15900.0</td>
      <td>538</td>
    </tr>
    <tr>
      <th>Venture - Series Unknown</th>
      <td>3.882314e+10</td>
      <td>1.072462e+08</td>
      <td>3.300000e+09</td>
      <td>106664.0</td>
      <td>362</td>
    </tr>
    <tr>
      <th>Series D</th>
      <td>3.902133e+10</td>
      <td>1.111719e+08</td>
      <td>1.400000e+09</td>
      <td>178800.0</td>
      <td>351</td>
    </tr>
    <tr>
      <th>Series E</th>
      <td>4.110088e+10</td>
      <td>1.599256e+08</td>
      <td>1.500000e+09</td>
      <td>438942.0</td>
      <td>257</td>
    </tr>
    <tr>
      <th>Debt Financing</th>
      <td>2.975907e+10</td>
      <td>1.322625e+08</td>
      <td>2.000000e+09</td>
      <td>25000.0</td>
      <td>225</td>
    </tr>
    <tr>
      <th>Post-IPO Equity</th>
      <td>1.072456e+11</td>
      <td>5.499772e+08</td>
      <td>1.378712e+10</td>
      <td>241000.0</td>
      <td>195</td>
    </tr>
    <tr>
      <th>Series F</th>
      <td>3.316825e+10</td>
      <td>2.319458e+08</td>
      <td>4.000000e+09</td>
      <td>8040000.0</td>
      <td>143</td>
    </tr>
    <tr>
      <th>Private Equity</th>
      <td>7.204112e+10</td>
      <td>5.182814e+08</td>
      <td>5.500000e+09</td>
      <td>2000000.0</td>
      <td>139</td>
    </tr>
    <tr>
      <th>Grant</th>
      <td>4.366330e+09</td>
      <td>5.077128e+07</td>
      <td>1.600000e+09</td>
      <td>6500.0</td>
      <td>86</td>
    </tr>
    <tr>
      <th>Post-IPO Debt</th>
      <td>8.388809e+10</td>
      <td>1.035655e+09</td>
      <td>1.200000e+10</td>
      <td>1800000.0</td>
      <td>81</td>
    </tr>
    <tr>
      <th>Pre-Seed</th>
      <td>2.725625e+07</td>
      <td>3.539772e+05</td>
      <td>2.700000e+06</td>
      <td>15900.0</td>
      <td>77</td>
    </tr>
    <tr>
      <th>Corporate Round</th>
      <td>3.666688e+10</td>
      <td>4.954984e+08</td>
      <td>5.228880e+09</td>
      <td>200000.0</td>
      <td>74</td>
    </tr>
    <tr>
      <th>Series G</th>
      <td>1.694313e+10</td>
      <td>2.647364e+08</td>
      <td>3.500000e+09</td>
      <td>10000000.0</td>
      <td>64</td>
    </tr>
    <tr>
      <th>Angel</th>
      <td>7.499975e+07</td>
      <td>1.209673e+06</td>
      <td>1.000000e+07</td>
      <td>40000.0</td>
      <td>62</td>
    </tr>
    <tr>
      <th>Convertible Note</th>
      <td>3.642194e+09</td>
      <td>6.389813e+07</td>
      <td>2.400000e+09</td>
      <td>20000.0</td>
      <td>57</td>
    </tr>
    <tr>
      <th>Secondary Market</th>
      <td>7.968410e+09</td>
      <td>1.448802e+08</td>
      <td>2.000000e+09</td>
      <td>800000.0</td>
      <td>55</td>
    </tr>
    <tr>
      <th>Equity Crowdfunding</th>
      <td>2.482259e+08</td>
      <td>5.516130e+06</td>
      <td>5.654358e+07</td>
      <td>33982.0</td>
      <td>45</td>
    </tr>
    <tr>
      <th>Funding Round</th>
      <td>3.921870e+09</td>
      <td>1.120534e+08</td>
      <td>1.000000e+09</td>
      <td>300000.0</td>
      <td>35</td>
    </tr>
    <tr>
      <th>Series H</th>
      <td>8.898700e+09</td>
      <td>2.966233e+08</td>
      <td>1.096300e+09</td>
      <td>20000000.0</td>
      <td>30</td>
    </tr>
    <tr>
      <th>Initial Coin Offering</th>
      <td>4.542700e+09</td>
      <td>4.129727e+08</td>
      <td>4.100000e+09</td>
      <td>1300000.0</td>
      <td>11</td>
    </tr>
    <tr>
      <th>Series J</th>
      <td>2.284939e+09</td>
      <td>2.284939e+08</td>
      <td>8.000000e+08</td>
      <td>5100000.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>Post-IPO Secondary</th>
      <td>1.459822e+10</td>
      <td>1.622024e+09</td>
      <td>3.135000e+09</td>
      <td>1060000.0</td>
      <td>9</td>
    </tr>
    <tr>
      <th>Series I</th>
      <td>1.174140e+09</td>
      <td>1.304600e+08</td>
      <td>2.140000e+08</td>
      <td>39740000.0</td>
      <td>9</td>
    </tr>
    <tr>
      <th>Product Crowdfunding</th>
      <td>1.403200e+07</td>
      <td>2.338667e+06</td>
      <td>1.100000e+07</td>
      <td>100000.0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>Non-equity Assistance</th>
      <td>3.855000e+05</td>
      <td>7.710000e+04</td>
      <td>1.855000e+05</td>
      <td>50000.0</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-b08e4d2c-7993-48e0-8bec-c4f867dcc418')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-b08e4d2c-7993-48e0-8bec-c4f867dcc418 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-b08e4d2c-7993-48e0-8bec-c4f867dcc418');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""We check the third data set. Noticed all the data is not numeric.
5289 acquisitions with 497 unique buyers and 106 categories of ACQUISITION_TYPE	 """

ACQ.describe(include='all').T 
```





  <div id="df-c008091f-c33f-45d3-b95a-4d71b01057ca">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>unique</th>
      <th>top</th>
      <th>freq</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>COMPANY_NAME</th>
      <td>5289</td>
      <td>497</td>
      <td>Microsoft</td>
      <td>235</td>
    </tr>
    <tr>
      <th>ACQUIREE_NAME</th>
      <td>5289</td>
      <td>4167</td>
      <td>Fastlane</td>
      <td>4</td>
    </tr>
    <tr>
      <th>ANNOUNCED_DATE</th>
      <td>5289</td>
      <td>2691</td>
      <td>May 6, 2021</td>
      <td>16</td>
    </tr>
    <tr>
      <th>PRICE</th>
      <td>5289</td>
      <td>560</td>
      <td>—</td>
      <td>3949</td>
    </tr>
    <tr>
      <th>ACQUISITION_TYPE</th>
      <td>5289</td>
      <td>6</td>
      <td>Acquisition</td>
      <td>4087</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-c008091f-c33f-45d3-b95a-4d71b01057ca')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-c008091f-c33f-45d3-b95a-4d71b01057ca button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-c008091f-c33f-45d3-b95a-4d71b01057ca');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""The Top Ten companies with most acquistions.
Microsoft , Cisco and Google fighting realy close to get the top1 """
ACQ2 = ACQ.groupby('COMPANY_NAME').agg({'ACQUIREE_NAME': np.count_nonzero})
ACQ3 = ACQ2.sort_values([('ACQUIREE_NAME')], ascending=False).head(10)
ACQ3
```





  <div id="df-51de4228-e9dc-4580-956a-375d664df71e">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ACQUIREE_NAME</th>
    </tr>
    <tr>
      <th>COMPANY_NAME</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Microsoft</th>
      <td>235</td>
    </tr>
    <tr>
      <th>Cisco</th>
      <td>233</td>
    </tr>
    <tr>
      <th>Google</th>
      <td>230</td>
    </tr>
    <tr>
      <th>Accenture</th>
      <td>215</td>
    </tr>
    <tr>
      <th>EQT</th>
      <td>175</td>
    </tr>
    <tr>
      <th>IBM</th>
      <td>172</td>
    </tr>
    <tr>
      <th>Oracle</th>
      <td>123</td>
    </tr>
    <tr>
      <th>Apple</th>
      <td>113</td>
    </tr>
    <tr>
      <th>Intel</th>
      <td>97</td>
    </tr>
    <tr>
      <th>Facebook</th>
      <td>88</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-51de4228-e9dc-4580-956a-375d664df71e')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-51de4228-e9dc-4580-956a-375d664df71e button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-51de4228-e9dc-4580-956a-375d664df71e');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""In the flowwing plot scatter we compare the total amount raised with the number of accquistion made.
We notice there is not direct correlation between thesse two variables.
The explanation can be that the companies with more accquisition are big companies
wich are consolidated and aren´t raising funds. By the other hand companies with high number of money 
raised are young companies and haven´t make much accquisitions.
 """

INAC = INV4.merge(ACQ2 ,on = 'COMPANY_NAME', how= 'left')
INAC.plot.scatter(x= [('ACQUIREE_NAME')], y = [('M_R_USD', 'sum')])
```

    /usr/local/lib/python3.8/dist-packages/pandas/core/frame.py:9190: FutureWarning: merging between different levels is deprecated and will be removed in a future version. (2 levels on the left,1 on the right)
      return merge(





    <matplotlib.axes._subplots.AxesSubplot at 0x7f6cd22a2580>




    
![png](output_17_2.png)
    



```python
"""Here we want to validate the past conclusion , by aggruping the accqusitions numbers whith the revenu_range of companies.
We can see the companies with $10B+ REVENU_RANGE had both the highest average and total acquistions.
We see a correlation between Revenu_range and accquisiton mean and sum.
 """

COMA = COM.merge(ACQ2 ,on = 'COMPANY_NAME', how= 'left')
COMA2 = COMA.groupby('REVENU_RANGE').agg({'ACQUIREE_NAME': [np.mean,np.sum, np.max, np.min, np.count_nonzero]})
COMA3 = COMA2.sort_values([('ACQUIREE_NAME','mean')], ascending=False)
COMA3

```





  <div id="df-be9e70b3-ab35-4391-a684-45151204c031">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="5" halign="left">ACQUIREE_NAME</th>
    </tr>
    <tr>
      <th></th>
      <th>mean</th>
      <th>sum</th>
      <th>amax</th>
      <th>amin</th>
      <th>count_nonzero</th>
    </tr>
    <tr>
      <th>REVENU_RANGE</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>$10B+</th>
      <td>40.250000</td>
      <td>1449.0</td>
      <td>233.0</td>
      <td>1.0</td>
      <td>42</td>
    </tr>
    <tr>
      <th>$1B to $10B</th>
      <td>21.031746</td>
      <td>1325.0</td>
      <td>235.0</td>
      <td>1.0</td>
      <td>77</td>
    </tr>
    <tr>
      <th>$500M to $1B</th>
      <td>11.583333</td>
      <td>417.0</td>
      <td>80.0</td>
      <td>1.0</td>
      <td>47</td>
    </tr>
    <tr>
      <th>$100M to $500M</th>
      <td>7.066667</td>
      <td>848.0</td>
      <td>175.0</td>
      <td>1.0</td>
      <td>166</td>
    </tr>
    <tr>
      <th>$10M to $50M</th>
      <td>6.115385</td>
      <td>636.0</td>
      <td>215.0</td>
      <td>1.0</td>
      <td>216</td>
    </tr>
    <tr>
      <th>$50M to $100M</th>
      <td>5.500000</td>
      <td>341.0</td>
      <td>52.0</td>
      <td>1.0</td>
      <td>103</td>
    </tr>
    <tr>
      <th>$1M to $10M</th>
      <td>3.965517</td>
      <td>230.0</td>
      <td>62.0</td>
      <td>1.0</td>
      <td>230</td>
    </tr>
    <tr>
      <th>Less than $1M</th>
      <td>2.833333</td>
      <td>34.0</td>
      <td>7.0</td>
      <td>1.0</td>
      <td>73</td>
    </tr>
    <tr>
      <th>—</th>
      <td>1.500000</td>
      <td>9.0</td>
      <td>3.0</td>
      <td>1.0</td>
      <td>46</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-be9e70b3-ab35-4391-a684-45151204c031')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-be9e70b3-ab35-4391-a684-45151204c031 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-be9e70b3-ab35-4391-a684-45151204c031');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""We check the Employee data set. Noticed all the data is not numeric.
20702 Employees in 964 comapines,  12308 different JOB_TITLES and 2973 who ATTENDED_SCHOOLS.
The most common job tittle is Software Engineer and the most attended_school is Stanford	 """

EMP.describe(include='all').T 
```





  <div id="df-566de9a6-371f-4295-a71d-26ac72a08fc2">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>unique</th>
      <th>top</th>
      <th>freq</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>EMPLOYEE_MD5</th>
      <td>20702</td>
      <td>20702</td>
      <td>aac4a9fe0edc50a77072eae64578a892</td>
      <td>1</td>
    </tr>
    <tr>
      <th>JOB_TITLES</th>
      <td>20702</td>
      <td>12308</td>
      <td>Software Engineer</td>
      <td>510</td>
    </tr>
    <tr>
      <th>COMPANY_NAME</th>
      <td>20702</td>
      <td>964</td>
      <td>Microsoft</td>
      <td>1756</td>
    </tr>
    <tr>
      <th>ATTENDED_SCHOOLS</th>
      <td>6584</td>
      <td>2973</td>
      <td>Stanford University</td>
      <td>159</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-566de9a6-371f-4295-a71d-26ac72a08fc2')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-566de9a6-371f-4295-a71d-26ac72a08fc2 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-566de9a6-371f-4295-a71d-26ac72a08fc2');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""The Top Ten companies with employees which attended schools.
Microsoft and Google leading with an a important distance.
All companies are tech-companies """

EMP2 = EMP.groupby('COMPANY_NAME').agg({'ATTENDED_SCHOOLS': np.count_nonzero})
EMP3 = EMP2.sort_values([('ATTENDED_SCHOOLS')], ascending=False).head(10)
EMP3
```





  <div id="df-599a82fa-75f5-460c-8fa3-6e298afcc899">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ATTENDED_SCHOOLS</th>
    </tr>
    <tr>
      <th>COMPANY_NAME</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Microsoft</th>
      <td>1756</td>
    </tr>
    <tr>
      <th>Google</th>
      <td>1598</td>
    </tr>
    <tr>
      <th>Facebook</th>
      <td>636</td>
    </tr>
    <tr>
      <th>Intel</th>
      <td>626</td>
    </tr>
    <tr>
      <th>IBM</th>
      <td>593</td>
    </tr>
    <tr>
      <th>Cisco</th>
      <td>474</td>
    </tr>
    <tr>
      <th>SAP</th>
      <td>394</td>
    </tr>
    <tr>
      <th>Accenture</th>
      <td>316</td>
    </tr>
    <tr>
      <th>Uber</th>
      <td>291</td>
    </tr>
    <tr>
      <th>Oracle</th>
      <td>279</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-599a82fa-75f5-460c-8fa3-6e298afcc899')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-599a82fa-75f5-460c-8fa3-6e298afcc899 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-599a82fa-75f5-460c-8fa3-6e298afcc899');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""69 out of 157 CEO attended to schools.
Each of them attended to different schools"""

EMP4 = EMP[(EMP['JOB_TITLES']=='CEO')]
EMP4.describe(include='all').T 
```





  <div id="df-1802be8d-7414-44eb-9468-fd46f9afb5ee">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>unique</th>
      <th>top</th>
      <th>freq</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>EMPLOYEE_MD5</th>
      <td>157</td>
      <td>157</td>
      <td>aac4a9fe0edc50a77072eae64578a892</td>
      <td>1</td>
    </tr>
    <tr>
      <th>JOB_TITLES</th>
      <td>157</td>
      <td>1</td>
      <td>CEO</td>
      <td>157</td>
    </tr>
    <tr>
      <th>COMPANY_NAME</th>
      <td>157</td>
      <td>154</td>
      <td>Microsoft</td>
      <td>2</td>
    </tr>
    <tr>
      <th>ATTENDED_SCHOOLS</th>
      <td>69</td>
      <td>69</td>
      <td>Indian Institute of Technology Kharagpur Stan...</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-1802be8d-7414-44eb-9468-fd46f9afb5ee')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-1802be8d-7414-44eb-9468-fd46f9afb5ee button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-1802be8d-7414-44eb-9468-fd46f9afb5ee');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
"""The final table we group by REVENU_RANGE	the mean: 
M_R_USD (money colected) and ATTENDED_SCHOOLS
There is a positive relation between revenu_range and the mean 
of the attended_schools.
 """

COMAE = COMA.merge(EMP2 ,on = 'COMPANY_NAME', how= 'left')
COMAEI = COMAE.merge(INV2 ,on = 'COMPANY_NAME', how= 'left')
COMAEI2 = COMAEI.groupby('REVENU_RANGE').agg({'M_R_USD': [np.mean],
                                              'ATTENDED_SCHOOLS': [np.mean],
                                            })
COMAEI3 = COMAEI2.sort_values([('M_R_USD','mean')], ascending=False)
COMAEI3 
```





  <div id="df-8f745af6-f9f7-4dc4-8447-b0592ea11a24">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th>M_R_USD</th>
      <th>ATTENDED_SCHOOLS</th>
    </tr>
    <tr>
      <th></th>
      <th>mean</th>
      <th>mean</th>
    </tr>
    <tr>
      <th>REVENU_RANGE</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>$10B+</th>
      <td>7.120653e+08</td>
      <td>249.586207</td>
    </tr>
    <tr>
      <th>$1B to $10B</th>
      <td>4.365372e+08</td>
      <td>43.329231</td>
    </tr>
    <tr>
      <th>$500M to $1B</th>
      <td>3.064585e+08</td>
      <td>17.659498</td>
    </tr>
    <tr>
      <th>$100M to $500M</th>
      <td>1.503932e+08</td>
      <td>17.797841</td>
    </tr>
    <tr>
      <th>$50M to $100M</th>
      <td>9.262683e+07</td>
      <td>10.703226</td>
    </tr>
    <tr>
      <th>$10M to $50M</th>
      <td>7.522459e+07</td>
      <td>10.238715</td>
    </tr>
    <tr>
      <th>$1M to $10M</th>
      <td>3.570581e+07</td>
      <td>5.696629</td>
    </tr>
    <tr>
      <th>—</th>
      <td>3.283981e+07</td>
      <td>4.087912</td>
    </tr>
    <tr>
      <th>Less than $1M</th>
      <td>1.905546e+07</td>
      <td>4.883895</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-8f745af6-f9f7-4dc4-8447-b0592ea11a24')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-8f745af6-f9f7-4dc4-8447-b0592ea11a24 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-8f745af6-f9f7-4dc4-8447-b0592ea11a24');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>



