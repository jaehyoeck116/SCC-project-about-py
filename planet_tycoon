# Planet simulator
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

fig, ax = plt.subplots()
color = ['#eb4034', '#383636', '#dae632', '#1d79cf', '#b53921', '#cc7f02', '#ad7417', '#0786b0', '#08c9b0']
ax.scatter([0, 0.39, 0.7, 1, 1.52, 5, 10, 20, 30], [0, 0, 0, 0, 0, 0, 0, 0, 0], color=color)
x = [0, 0.39, 0.7, 1, 1.52, 5, 10, 20, 30]
y = [0, 0, 0, 0, 0, 0, 0, 0, 0]
vx = [0, 0, 0, 0, 0, 0, 0, 0, 0]
vy = [0, 4.8, 3.59, 3, 2.43, 1.34, 0.95, 0.67, 0.55]
Ax = [0, 0, 0, 0, 0, 0, 0, 0, 0]
Ay = [0, 0, 0, 0, 0, 0, 0, 0, 0]
dt = 0.01

plt.xlim(-50, 50)
plt.ylim(-50, 50)
k = 100


def acc(i, j):
    l = 9
    value = l / (i ** 2 + j ** 2)
    len = (i ** 2 + j ** 2) ** (1 / 2)
    vector = (-i, -j)
    Ax, Ay = (-i * value / len, -j * value / len)
    # Ax, Ay = (-i*value, -j*value)
    return (Ax, Ay)


def animation(i):
    for i in range(1, 9):
        a, b = acc(x[i], y[i])
        Ax[i] = a
        Ay[i] = b
        vx[i] += Ax[i] * dt
        vy[i] += Ay[i] * dt
        x[i] += vx[i] * dt
        y[i] += vy[i] * dt

    plt.cla()
    plt.xlim(-50, 50)
    plt.ylim(-50, 50)
    ax.scatter(x, y, color=color)  # ax.scatter(x,y, color = color) 지동설


animation1 = FuncAnimation(fig, func=animation, interval=1, blit=False)

plt.show()
