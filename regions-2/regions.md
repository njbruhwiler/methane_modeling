

```python
def nat_read_xlsx(xrow1,xrow2,xcol):
    import xlrd
    file = 'RegionalTotals.xlsx'
    wb=xlrd.open_workbook(file)
    sheet=wb.sheet_by_index(0)
    data=[]
    for i in range (xrow1,xrow2):
        data.append(sheet.cell_value(i,xcol))
    return data
```


```python
year=nat_read_xlsx(3,18,1)
```


```python
year
```




    [2015.0,
     2014.0,
     2013.0,
     2012.0,
     2011.0,
     2010.0,
     2009.0,
     2008.0,
     2007.0,
     2006.0,
     2005.0,
     2004.0,
     2003.0,
     2002.0,
     2001.0]




```python
Africa_total=nat_read_xlsx(3,18,9)
```


```python
Africa_total
```




    [5.13904502454452,
     5.091980666039379,
     4.9774846277507105,
     4.820281803777588,
     4.712644121326075,
     4.572478032335458,
     4.478424011399621,
     4.376103547923359,
     4.114392436949098,
     4.0507795560875826,
     3.9473183461540446,
     3.81786684078999,
     3.781469551114946,
     3.6980636751291893,
     3.5928008506278863]




```python
Latin_America_total=nat_read_xlsx(19,34,9)
```


```python
Latin_America_total
```




    [1.59366189742339,
     1.6173540537599786,
     1.6784387875913287,
     1.6983370896292347,
     1.6882865911450569,
     1.6881874882088588,
     1.615553697603017,
     1.7213575013607214,
     1.751960536468614,
     1.705819040915052,
     1.673110825142389,
     1.638710236050889,
     1.5907834321653156,
     1.5106292906332703,
     1.413202900634338]




```python
Asia_total=nat_read_xlsx(35,50,9)
```


```python
Asia_total
```




    [6.57197728192206,
     6.612883954402587,
     6.504586474935306,
     6.466148336211333,
     6.331040858173906,
     6.185005035818503,
     6.073869411008377,
     6.258503283001529,
     6.217392981804375,
     5.970280032268255,
     5.915249662852172,
     5.857865474805899,
     5.794027169044317,
     5.77089777954221,
     5.639322625657893]




```python
North_America_total=nat_read_xlsx(51,66,9)
```


```python
North_America_total
```




    [2.582733909083802,
     2.8164433972859806,
     2.7506263735240073,
     2.596695324778388,
     2.544634740455457,
     2.6322284320542013,
     2.2952684698546837,
     2.4741685149289987,
     2.516342464787454,
     2.556447413483996,
     2.630546170641197,
     2.6316904123404528,
     2.588225046963389,
     2.3432488641612714,
     2.4526584313315705]




```python
Europe_total=nat_read_xlsx(67,82,9)
```


```python
Europe_total
```




    [1.6833856343047444,
     1.5242911527785297,
     1.5456945058988958,
     1.5274006322797034,
     1.599760716753243,
     1.6290567479037137,
     1.5182114553018395,
     1.4805242739420725,
     1.3604070952864498,
     1.2737131483040138,
     1.3489829643415703,
     1.2979999454897417,
     1.3196694386283154,
     1.9445460440929856,
     1.8658090764346031]




```python
Global_total=nat_read_xlsx(84,99,9)
```


```python
Global_total
```




    [17.594815096718584,
     17.686376192338706,
     17.479617453907146,
     17.131120612647784,
     16.89828680388165,
     16.721787212624513,
     15.995287643455443,
     16.32369256142707,
     15.97217190606899,
     15.568913393146325,
     15.526490482871484,
     15.255057269414854,
     15.084788758623034,
     15.27766374849454,
     14.973737092176398]




```python
import numpy
```


```python
from matplotlib import pyplot, axes
from scipy import stats
```


```python
pyplot.plot(year,Africa_total,color='orange')
m, b, r_value, p_value, std_err = stats.linregress(year, Africa_total)
print(m)
print(std_err) 
pyplot.plot(year,Latin_America_total,color='green')
m, b, r_value, p_value, std_err = stats.linregress(year, Latin_America_total)
print(m)
print(std_err) 
pyplot.plot(year,Asia_total,color='red')
m, b, r_value, p_value, std_err = stats.linregress(year, Asia_total)
print(m)
print(std_err) 
pyplot.plot(year,North_America_total,color='blue')
m, b, r_value, p_value, std_err = stats.linregress(year, North_America_total)
print(m)
print(std_err) 
pyplot.plot(year,Europe_total,color='purple')
m, b, r_value, p_value, std_err = stats.linregress(year, Europe_total)
print(m)
print(std_err)  
pyplot.legend(['Africa .117 ± .003', 'Latin America .009 ± .005','Asia .068 ± .005','North America .015 ± .007','Europe .000 ± .012'])
pyplot.xlabel("Year")
pyplot.ylabel("Methane Emissions in Tg/Yr")
pyplot.title("Biofuel Methane Emissions from 2001 to 2015")
pyplot.rcParams['figure.figsize']=(20,10)
```

    0.11742982946596124
    0.0031719162011029727
    0.008765011076632436
    0.004873313771864529
    0.06821331300127789
    0.0045332426361023755
    0.014623127061496887
    0.007381278329162914
    -0.0004640733672613956
    0.012301689793565728



![png](output_17_1.png)



```python

```
