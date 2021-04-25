import matplotlib as mpl
import matplotlib.pyplot as plt
import pandas as pd
import calmap

df = pd.read_csv('source/fires_for_python2018_2020.csv', parse_dates = ['date'])
df['year'] = df.date.dt.year
df.set_index('date', inplace = True)
df18 = df.query('year == 2018')

def get_plot(df, k):
    plt.figure(figsize = (16, 10), dpi = 300)
    fig, ax = calmap.calendarplot(df, cmap = 'magma_r'
                   , fig_kws={'figsize': (16,10)} 
                   , yearlabel_kws = {'color':'black', 'fontsize':20})
    n = [num*3 for num in range(k)]
    fig.colorbar(ax[0].get_children()[1], ax=ax.ravel().tolist()
                 , orientation='vertical'
                 , shrink = 0.18).set_ticks(n).tick_params(labelsize = 12)
    return plt.show()
    
    get_plot(df18['2018']['numOfFires'], df18.numOfFires.max())
