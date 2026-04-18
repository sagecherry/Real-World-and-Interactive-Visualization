# Real-World-and-Interactive-Visualization
## Theory

This experiment demonstrates advanced interactive and real-world data visualization techniques using libraries such as Plotly, Matplotlib, and SciPy. These visualizations help in exploring complex relationships, hierarchies, and multi-dimensional data in an engaging and insightful manner.

The notebook covers the following:

1. Importing required libraries  
   ```python
   import pandas as pd
   import plotly.express as px
   import plotly.graph_objects as go
   import matplotlib.pyplot as plt
   from scipy.cluster.hierarchy import dendrogram, linkage
   from matplotlib_venn import venn2
   ```  
   Pandas is used for data handling, Plotly for interactive charts, Matplotlib for static plots, and SciPy for hierarchical clustering.

2. Treemap Chart using Plotly Express  
   ```python
   df = pd.DataFrame({
       'Department': ['HR', 'IT', 'Sales', 'Marketing'],
       'Budget': [20000, 50000, 40000, 30000]
   })
   fig = px.treemap(df, path=['Department'], values='Budget', title='Treemap of Department vs Budget')
   fig.show()
   ```  
   Treemap visualizes hierarchical data using nested rectangles, where size represents values. It is useful for budget allocation or category breakdowns.

3. Dendrogram using SciPy and Matplotlib  
   ```python
   data = np.array([[5,3],[10,15],[15,12],[24,10],[30,30]])
   linked = linkage(data, method='ward')
   plt.figure(figsize=(6,6))
   dendrogram(linked)
   plt.xlabel("Data Points")
   plt.ylabel("Distance")
   plt.show()
   ```  
   Dendrogram shows hierarchical clustering results. The 'ward' method minimizes variance within clusters. It is commonly used in taxonomy or customer segmentation.

4. Venn Diagram using matplotlib_venn  
   ```python
   A = {1,2,3,4}
   B = {3,4,5,6}
   venn2([A,B], set_labels=('Set A','Set B'))
   plt.title("Venn Diagram")
   plt.show()
   ```  
   Venn diagram illustrates logical relationships between sets using overlapping circles. It helps in understanding intersections and unions.

5. Sankey Diagram using Plotly Graph Objects  
   ```python
   fig = go.Figure(data=[go.Sankey(
       node=dict(label=["Admission","First Year","Second Year","Placed"]),
       link=dict(source=[0,1,2], target=[1,2,3], value=[100,80,60])
   )])
   fig.show()
   ```  
   Sankey diagram visualizes flow between stages or categories. It is effective for showing student progression, resource allocation, or process flows.

6. 3D Scatter Plot using Plotly Express  
   ```python
   df = pd.DataFrame({
       'Study_Hours': [2,4,6,8,5],
       'Marks': [50,65,75,90,70],
       'Attendance': [60,75,80,90,70]
   })
   fig = px.scatter_3d(df, x='Study_Hours', y='Marks', z='Attendance', title="Student Performance Analysis")
   fig.show()
   ```  
   3D scatter plot shows relationships between three numerical variables. It helps in multi-dimensional analysis like performance metrics.

7. Radar Chart using Plotly Graph Objects  
   ```python
   skills = ['Python','ML','DBMS','DSA','Communication']
   values = [4,3,5,4,3]
   fig = go.Figure()
   fig.add_trace(go.Scatterpolar(r=values, theta=skills, fill='toself', name='Student Skills'))
   fig.show()
   ```  
   Radar chart (spider chart) compares multiple variables on a circular axis. It is useful for skill assessment or performance profiling.

These visualizations help in:
- Exploring hierarchical and flow-based data
- Understanding multi-dimensional relationships
- Presenting comparative and set-based analysis

## Conclusion

The experiment successfully demonstrated how to:
- Create interactive charts using Plotly for real-world data exploration
- Generate hierarchical, set-based, and multi-dimensional visualizations
- Use advanced techniques like treemaps, dendrograms, Sankey diagrams, 3D plots, and radar charts

These interactive visualizations are essential for communicating insights effectively in data analysis, business intelligence, and academic reporting.
