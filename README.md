# Quantitative-comparisons
## Introduce our basic quantitative data:

This is simple data about olympiad, ten countries each of them earned a gold, sliver and bronze medals <br />
our mission is to make comparisons and analysis for this data:

![image](https://user-images.githubusercontent.com/43391147/126034931-f1a99f84-58a3-4e27-a0d0-0dde22913e90.png)

## Lets plot and see the problems:

```
# import data from csv file
pd = pd.read_csv('medals.csv')

fig, ax = plt.subplots()
# customize our plot label 'Gold'
ax.bar(pd['Unnamed: 0'], pd['Gold'], label='Gold')

plt.legend()
plt.show()
```

![image](https://user-images.githubusercontent.com/43391147/126035081-cb7e80a0-8df3-4f80-bf92-621eec27b5c3.png)

First problem we can see here: the names on x-axis<br />
to fix that we need to rotate the names only by 90 degree<br />
We will add function 'set_xticklabels()':

```
ax.set_xticklabels(pd['Unnamed: 0'], pd['Gold'], label='Gold')
```

![image](https://user-images.githubusercontent.com/43391147/126035161-962b8207-a613-44a5-a014-254b14afafaf.png)

**so far so good...**

## Let's add the other elements in this comparison:

Add silver:<br />

```
ax.bar(medals.index, medals.Silver, bottom=medals.Gold, label='Silver')
```

Same for bronze:<br />

```
# Stack bars for "Bronze" on top of that with label "Bronze"
ax.bar(medals.index, medals['Bronze'], bottom=medals["Gold"] + medals["Silver"], label='Bronze')
```

**And now :**

![image](https://user-images.githubusercontent.com/43391147/126035332-f8322888-6d84-43e0-9129-d21a6e95b677.png)

Look good for now...

## Explore the distribution of data

Now we will use larger dataset for this case, our data simpily will be comparison of men hights in two different sprots (Gymnastics, Rowing)

**Gymnastics men data:**

![image](https://user-images.githubusercontent.com/43391147/126051549-8a0abc6c-2a9a-47de-b179-23a2133b5ad4.png)
<br />

**Rowing men data:**

![image](https://user-images.githubusercontent.com/43391147/126051566-8b3b700b-692a-483a-ad41-a397a6429451.png)

<br />

**Let's Hist it**

```
# customize the bin or the interval for 5 only, the default is 10
ax.hist(men_rowing['Height'], label='rowing', bins=5)
ax.hist(men_gymnastics['Height'], label='gymnastics', bins=5)
# labeling xy axis for 
ax.set_xlabel('Heights of men')
ax.set_ylabel('# of observation')
plt.legend()
plt.show()
```

Now we get this:

![image](https://user-images.githubusercontent.com/43391147/126051754-e2e78f65-533f-41af-9fc6-1d5be871b5c1.png)

<br />

Look good, but we can modify to read it easy, by adding 'hisstype' attribute <br />

```
ax.hist(men_rowing['Height'], label='rowing', bins=5, histtype='step')
ax.hist(men_gymnastics['Height'], label='gymnastics', bins=5, histtype='step')
```

![image](https://user-images.githubusercontent.com/43391147/126051780-db94ec81-a1d7-4ace-863b-00c217791f8a.png)
<br />

We can see now most of gymnastic players below under 180CM <br />
And rowing players are taller than gymnastic players and their heights concentrated in the interval between 180:198<br>




