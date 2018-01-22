

```python
import pandas as pd
```


```python
location = r'D:\test.csv'
data = pd.read_csv(location)
```


```python
print (data)
```

               name  movementSpeed  physicalAttack  armor    hp  mana
    0         Layla            270             118     15  2500   424
    1       Cyclops            250             107     18  2461   500
    2      Minotaur            265             123     25  2705     0
    3         Saber            265             121     17  2475   443
    4         Roger            235             120     22  2580   450
    5          Nana            250             110     17  2325   499
    6          Akai            260             115     24  2769   422
    7         Alice            240             109     21  2397   493
    8         Alpha            236             121     20  2646   453
    9       Alucard            265             118     21  2593     0
    10        Argus            260             124     21  2628     0
    11       Aurora            245             105     17  2441   500
    12      Balmond            265             114     23  2602     0
    13         Bane            265             117     23  2625   433
    14        Bruno            240             116     17  2402   439
    15         Chou            265             121     23  2598     0
    16        Clint            248             122     20  2500   450
    17       Diggie            250             115     16  2351   490
    18        Estes            240             115     13  2161   545
    19       Eudora            250             112     19  2524   468
    20        Fanny            270             126     17  2402     0
    21       Franco            255             116     25  2575   440
    22        Freya            265             109     22  2673   462
    23    Gatotkaca            260             120     20  2709   440
    24         Gord            240             105     13  2302   570
    25        Grock            260             135     21  2819   430
    26       Harley            240             114     19  2501   490
    27     Hayabusa            265             114     17  2555   479
    28       Helcur            255             121     17  2599   440
    29        Hilda            260             123     24  2909     0
    30        Hylos            260             105     17  3309   430
    31      Irithel            250             110     17  2540   438
    32      Johnson            255             112     27  2809     0
    33       Kagura            240             113     19  2380   519
    34       Karina            265             121     20  2505   431
    35       Karrie            240             112     17  2498   440
    36     Lancelot            260             124     16  2546   450
    37    Lapu-lapu            260             119     21  2628     0
    38       Lolita            265             115     27  2545     0
    39         Miya            235             114     17  2404   445
    40       Moskov            240             125     16  2530   420
    41      Natalia            265             121     18  2465   486
    42       Odette            240             105     18  2491   495
    43       Pharsa            240             109     15  2421   490
    44      Rafaela            245             112     15  2265   545
    45         Ruby            265             114     23  2709   430
    46   Sun Wukong            265             114     23  2630   400
    47      Tigreal            265             112     25  2756   450
    48       Vexana            245             112     17  2421   490
    49  Yi Sun-Shin            240             110     18  2520   438
    50     Yun Zhao            270             123     25  2561   405
    51        Zhask            240             107     15  2401   490
    


```python
Role = []
for i in range(len(data)):
    if data["movementSpeed"][i] >= 270:
        Role.append("MARKSMAN")
    elif data["mana"][i] >= 500:
        Role.append("MAGE")
    elif data["armor"][i] >= 25:
        Role.append("TANK")
    elif data["physicalAttack"][i] >= 121:
        Role.append("ASSASSIN")
    elif data["hp"][i] >= 2580:
        Role.append("FIGHTER")
    else:
        Role.append("SUPPORT")
```


```python
dp = pd.DataFrame({"name" : data["name"],"role" : Role})
```


```python
dp.to_csv("predictions.csv", index = False)
```


```python
dp
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>role</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Layla</td>
      <td>MARKSMAN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cyclops</td>
      <td>MAGE</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Minotaur</td>
      <td>TANK</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Saber</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Roger</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Nana</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Akai</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Alice</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Alpha</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Alucard</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Argus</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Aurora</td>
      <td>MAGE</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Balmond</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Bane</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Bruno</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Chou</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Clint</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Diggie</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Estes</td>
      <td>MAGE</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Eudora</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Fanny</td>
      <td>MARKSMAN</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Franco</td>
      <td>TANK</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Freya</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Gatotkaca</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Gord</td>
      <td>MAGE</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Grock</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Harley</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Hayabusa</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Helcur</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Hilda</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Hylos</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Irithel</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Johnson</td>
      <td>TANK</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Kagura</td>
      <td>MAGE</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Karina</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Karrie</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Lancelot</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Lapu-lapu</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Lolita</td>
      <td>TANK</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Miya</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Moskov</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Natalia</td>
      <td>ASSASSIN</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Odette</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Pharsa</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Rafaela</td>
      <td>MAGE</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Ruby</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Sun Wukong</td>
      <td>FIGHTER</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Tigreal</td>
      <td>TANK</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Vexana</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Yi Sun-Shin</td>
      <td>SUPPORT</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Yun Zhao</td>
      <td>MARKSMAN</td>
    </tr>
    <tr>
      <th>51</th>
      <td>Zhask</td>
      <td>SUPPORT</td>
    </tr>
  </tbody>
</table>
</div>


