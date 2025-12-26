import tkinter as tk
import tkinter.font as tkfont

# ASCII 
kali_ascii = r"""
⠀⠀⠀⠠⠤⠤⠤⠤⠤⣤⣤⣤⣄⣀⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠉⠛⠛⠿⢶⣤⣄⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⢀⣀⣀⣠⣤⣤⣴⠶⠶⠶⠶⠶⠶⠶⠶⠶⠶⠿⠿⢿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠚⠛⠉⠉⠉⠀⠀⠀⠀⠀⠀⢀⣀⣀⣤⡴⠶⠶⠿⠿⠿⣧⡀⠀⠀⠀⠤⢄⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢀⣠⡴⠞⠛⠉⠁⠀⠀⠀⠀⠀⠀⠀⢸⣿⣷⣶⣦⣤⣄⣈⡑⢦⣀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⣠⠔⠚⠉⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣾⡿⠟⠉⠉⠉⠉⠙⠛⠿⣿⣮⣷⣤⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣿⡿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⢻⣯⣧⡀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠻⢷⡤⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢿⣿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠻⣿⣦⣤⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠙⠛⠛⠻⠿⠿⣿⣶⣶⣦⣄⣀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠻⣿⣯⡛⠻⢦⡀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⢿⣆⠀⠙⢆⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢻⣆⠀⠈⢣
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠻⡆⠀⠈
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢻⡀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠃⠀
"""

WINDOW_SIZE = 550
BLACK = "#000000"

# window
root = tk.Tk()
root.geometry(f"{WINDOW_SIZE}x{WINDOW_SIZE}")
root.configure(bg=BLACK)
root.overrideredirect(True)
root.resizable(False, False)
root.attributes("-alpha", 1.0)
root.attributes("-topmost", True)

canvas = tk.Canvas(
    root,
    bg=BLACK,
    highlightthickness=0,
    bd=0,
    relief="flat"
)
canvas.pack(fill="both", expand=True)

# MOVE WINDOW 
offset_x = offset_y = 0

def start_move(event):
    global offset_x, offset_y
    offset_x = event.x
    offset_y = event.y

def do_move(event):
    x = root.winfo_pointerx() - offset_x
    y = root.winfo_pointery() - offset_y
    root.geometry(f"+{x}+{y}")

canvas.bind("<Button-1>", start_move)
canvas.bind("<B1-Motion>", do_move)

# font auto scale
lines = kali_ascii.splitlines()

font_size = 3
best_font = None
best_w = best_h = 0

while True:
    f = tkfont.Font(family="JetBrains Mono", size=font_size)
    w = max(f.measure(line) for line in lines)
    h = f.metrics("linespace") * len(lines)
    if w > WINDOW_SIZE or h > WINDOW_SIZE:
        break
    best_font = f
    best_w = w
    best_h = h
    font_size += 1

font = best_font
line_h = font.metrics("linespace")

x_start = (WINDOW_SIZE - best_w) // 2
y_start = (WINDOW_SIZE - best_h) // 2

# logo drawing
glow_layers = []

for i, line in enumerate(lines):
    y = y_start + i * line_h

    layers = []
    for dx, dy in [(-2,0),(2,0),(0,-2),(0,2),(-1,-1),(1,1)]:
        layers.append(
            canvas.create_text(
                x_start + dx,
                y + dy,
                text=line,
                fill="#001020",
                font=font,
                anchor="nw"
            )
        )

    canvas.create_text(
        x_start,
        y,
        text=line,
        fill="#ff3030",
        font=font,
        anchor="nw"
    )

    glow_layers.append(layers)

# oled
fade_rect = canvas.create_rectangle(
    0, 0, WINDOW_SIZE, WINDOW_SIZE,
    fill=BLACK,
    outline=""
)
canvas.tag_lower(fade_rect)

# animate 
glow_pos = len(lines)
frame = 0

def animate():
    global glow_pos, frame
    frame += 1

    # force full black redraw (kills gray bleed)
    canvas.itemconfig(fade_rect, fill=BLACK)

    for i, layers in enumerate(glow_layers):
        d = abs(i - glow_pos)
        if d <= 1:
            c = "#00ccff"
        elif d <= 3:
            c = "#0066cc"
        else:
            c = "#000810"   # absorbs light instead of glowing

        for item in layers:
            canvas.itemconfig(item, fill=c)

    if frame % 2 == 0:
        glow_pos -= 1
        if glow_pos < 0:
            glow_pos = len(lines)

    root.after(33, animate)

animate()
root.mainloop()
