import tkinter as tk
from tkinter import messagebox

def caesar_cipher(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            base = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - base + shift) % 26 + base)
        else:
            result += char
    return result

def encrypt_message():
    text = entry_message.get()
    try:
        shift = int(entry_shift.get())
    except ValueError:
        messagebox.showerror("Invalid Input", "Shift value must be an integer")
        return
    encrypted = caesar_cipher(text, shift)
    output_result.config(text=f"Encrypted Text:\n{encrypted}")
    entry_message.delete(0, tk.END)
    entry_message.insert(0, encrypted)  # So you can decrypt it immediately

def decrypt_message():
    text = entry_message.get()
    try:
        shift = int(entry_shift.get())
    except ValueError:
        messagebox.showerror("Invalid Input", "Shift value must be an integer")
        return
    decrypted = caesar_cipher(text, -shift)
    output_result.config(text=f"Decrypted Text:\n{decrypted}")

# GUI setup
window = tk.Tk()
window.title("Caesar Cipher - Prodigy Infotech Task 1")
window.geometry("400x300")

tk.Label(window, text="Enter Text:").pack(pady=5)
entry_message = tk.Entry(window, width=50)
entry_message.pack()

tk.Label(window, text="Enter Shift Value:").pack(pady=5)
entry_shift = tk.Entry(window, width=10)
entry_shift.pack()

tk.Button(window, text="Encrypt", command=encrypt_message).pack(pady=10)
tk.Button(window, text="Decrypt", command=decrypt_message).pack()

output_result = tk.Label(window, text="", font=('Arial', 12), fg="blue", wraplength=380, justify="center")
output_result.pack(pady=20)

window.mainloop()
