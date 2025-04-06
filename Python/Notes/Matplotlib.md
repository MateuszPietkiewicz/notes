Created: 2025-04-06 08:50

---
Podstawowa aplikacja do wizualizacji w pythonie to matplotlib, która powstała na podstawie matlab'a.



```python
fig, ax = plt.subplots()
plt.show()
```

![[Pasted image 20250406085504.png]]



```python
seattle_avg_t = seattle_weather.groupby("DATE")["MLY-TAVG-NORMAL"].mean()

fig,  ax = plt.subplots()
ax.plot(seattle_avg_t)
plt.show()
```

![[Pasted image 20250406085613.png]]



```python
seattle_avg_prcp = seattle_weather.groupby("DATE")["MLY-PRCP-NORMAL"].mean()
austin_avg_prcp = austin_weather.groupby("DATE")["MLY-PRCP-NORMAL"].mean()

fig,  ax = plt.subplots()
ax.plot(seattle_avg_prcp.index, seattle_avg_prcp.values, color = "peru", marker = "o", linestyle="--")
ax.plot(austin_avg_prcp.index, austin_avg_prcp.values, color = "b", marker = "v", linestyle="-.")
plt.show()

```

![[Pasted image 20250406085707.png]]



```python
fig,  ax = plt.subplots()
ax.plot(seattle_avg_prcp.index, seattle_avg_prcp.values, color = "peru", marker = "o", linestyle="--", label="Magic")
ax.plot(austin_avg_prcp.index, austin_avg_prcp.values, color = "b", marker = "v", linestyle="-.", label="Yolo")

ax.set_xlabel("Time (months)")
ax.set_ylabel("Percipitation (inches)")

ax.set_title("Weather pattern in Austing and Seattle")
ax.legend()

plt.show()
```

![[Pasted image 20250406085752.png]]



```python
austin = austin_weather.groupby("DATE")[["MLY-PRCP-NORMAL","MLY-TAVG-NORMAL"]].mean()
seattle = seattle_weather.groupby("DATE")[["MLY-PRCP-NORMAL","MLY-TAVG-NORMAL"]].mean()

fig, ax = plt.subplots(2,2, sharey= 'col', sharex= True)
ax[0,0].plot(austin.index, austin["MLY-PRCP-NORMAL"])
ax[0,1].plot(austin.index, austin["MLY-TAVG-NORMAL"])

ax[1,0].plot(seattle.index, seattle["MLY-PRCP-NORMAL"])
ax[1,1].plot(seattle.index, seattle["MLY-TAVG-NORMAL"])
plt.show()
```

![[Pasted image 20250406085857.png]]



```python
def annotate_marker(df, ax, title="Max value",**arrowprops):
    max_idx, max_val = df["MLY-PRCP-NORMAL"].idxmax(), df["MLY-PRCP-NORMAL"].max()
    
    props = dict (arrowstyle="->", color ="m") | arrowprops
    
    ax.scatter( max_idx, max_val, color="green", marker="o")
    ax.annotate(title, 
               xy = (max_idx, max_val),
               xytext=(max_idx, max_val + 5),
               arrowprops=props
              )
```


```python
fig, ax = plt.subplots(2,1, sharey=True)

ax[0].plot(austin.index, austin["MLY-PRCP-NORMAL"],linestyle="-", color="b")
ax[0].plot(austin.index, austin["MLY-PRCP-25PCTL"], linestyle="--", color="b")
ax[0].plot(austin.index, austin["MLY-PRCP-75PCTL"], linestyle="--", color="b")
ax[0].axvline("Jan", color= "steelblue", linestyle= "--", linewidth=0.5)
ax[0].axhline(austin["MLY-PRCP-NORMAL"].max(), color= "steelblue", linestyle= "--", linewidth=0.5)

austin_max_idx, austin_max_prcp = austin["MLY-PRCP-NORMAL"].idxmax(), austin["MLY-PRCP-NORMAL"].max()

ax[0].scatter(austin_max_idx, austin_max_prcp, color="green", marker="o")
ax[0].annotate(f"Max avg month perception", 
               xy = (austin_max_idx, austin_max_prcp),
               xytext=(austin_max_idx, austin_max_prcp + 5),
               arrowprops=dict(arrowstyle="->", color="m")
              )

ax[1].plot(seattle.index, seattle["MLY-PRCP-NORMAL"], linestyle="-", color="r")
ax[1].plot(seattle.index, seattle["MLY-PRCP-25PCTL"], linestyle="--", color="r")
ax[1].plot(seattle.index, seattle["MLY-PRCP-75PCTL"], linestyle="--", color="r")
ax[1].axvline("Jul", color= "steelblue", linestyle= "--", linewidth=0.5)
annotate_marker(seattle, ax[1])


            

plt.show()
```

![[Pasted image 20250406090013.png]]




```python
fig, ax = plt.subplots( sharey=True)

ax.plot(austin.index, austin["MLY-PRCP-NORMAL"],linestyle="-", color="b")
ax.plot(austin.index, austin["MLY-PRCP-25PCTL"], linestyle="--", color="b")
ax.plot(austin.index, austin["MLY-PRCP-75PCTL"], linestyle="--", color="b")
ax.plot(seattle.index, seattle["MLY-PRCP-NORMAL"], linestyle="-", color="r")
ax.plot(seattle.index, seattle["MLY-PRCP-25PCTL"], linestyle="--", color="r")
ax.plot(seattle.index, seattle["MLY-PRCP-75PCTL"], linestyle="--", color="r")
plt.show()
```

![[Pasted image 20250406090059.png]]



```python
fig, ax = plt.subplots()

ax.bar(medals.index, medals["Gold"],color="Gold", label = "Gold")
ax.bar(medals.index, medals["Silver"],color="Silver", bottom=medals["Gold"], label = "Silver")
ax.bar(medals.index, medals["Bronze"],color="Brown", bottom=medals["Gold"] + medals["Silver"], label = "Bronze")

ax.set_xticks(range(len(medals.index)))
ax.set_xticklabels(medals.index, rotation = 90)
# mozna tak też
# ax.tick_params("x", rotation=90)

ax.set_ylabel("Number of medals")
ax.legend()
plt.show()
```

![[Pasted image 20250406090140.png]]



```python
import numpy as np
fig, ax = plt.subplots()

n= len(medals)
x = np.arange(n)

bar_width = 0.25

ax.bar(x - bar_width,  medals["Gold"], color="Gold", width= bar_width ,label = "Gold")
ax.bar(x, medals["Silver"], color="Silver",width= bar_width, label = "Silver")
ax.bar(x + bar_width, medals["Bronze"], color="Brown",width= bar_width, label = "Bronze")

ax.set_xticks(range(len(medals.index)))
ax.set_xticklabels(medals.index, rotation = 90)
# mozna tak też
# ax.tick_params("x", rotation=90)

ax.set_ylabel("Number of medals")
ax.legend()
plt.show()
```

![[Pasted image 20250406090207.png]]

---
Metadata:

Status: #pending
Tags: #wizualizacja #matplotlib
