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

