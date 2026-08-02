from tkinter import Tk, Label, Entry, Button

mode = "mile_to_km"

window = Tk()
window.title('mile to km converter')

mile_label = Label(window, text='Miles')
mile_label.grid(row=0, column=0, padx=10, pady=10, sticky="E")

Mile_entry = Entry(window, width=40)
Mile_entry.grid(row=0, column=1, pady=10, padx=(0, 10), sticky="W")

result_label = Label(window, )
result_label.grid(row=1, column=1, padx=(0, 10), pady=(0, 10), )


def calculate_button_click():
    try:
        value = float(Mile_entry.get())
    except ValueError:
        result_label.config(text="Please enter a numeric value", bg="red")
    else:
        if mode == "mile_to_km":
            calculate = value * 1.60934
            result_label.config(text=f'equal to {calculate} km', bg="green")
        else:
            mode == "km_to_mile"
            calculate = value / 1.60934
            result_label.config(text=f'equal to {calculate} miles', bg="green")


calculate_button = Button(window, text='calculate', command=calculate_button_click)
calculate_button.grid(row=2, column=1, pady=(0, 10), padx=(0, 10), sticky="W")


def change_km_to_mile():
    global mode

    if mode == "mile_to_km":
        mode = "km_to_mile"
        mile_label.config(text="Kilometers")
        change_button.config(text="mile to km")
    else:
        mode = "mile_to_km"
        mile_label.config(text="Miles")
        change_button.config(text="km to mile")


change_button = Button(window, text='km to mile', command=change_km_to_mile)
change_button.grid(row=2, column=0, pady=(0, 10), padx=(10, 10), sticky="W")

window.mainloop()
