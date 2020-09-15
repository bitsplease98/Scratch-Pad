# Scratch-Pad
Simple Text editor just like Notepad

## Technology Used:

1.Python Language

2.Tkinter Library

3.os module

## Sample Code

1.Creating the menubar and menu items

```
        self.menubar = Menu(root)
        filemenu = Menu(self.menubar, tearoff=0)  # tearoff = 0 => can't be seperated from window
        filemenu.add_command(label="New", underline=1, command=self.file_new, accelerator="Ctrl+N")
        filemenu.add_command(label="Open...", underline=1, command=self.file_open, accelerator="Ctrl+O")
        filemenu.add_command(label="Save", underline=1, command=self.file_save, accelerator="Ctrl+S")
        filemenu.add_command(label="Save As...", underline=5, command=self.file_save_as, accelerator="Ctrl+Alt+S")
        filemenu.add_separator()
        filemenu.add_command(label="Exit", underline=2, command=self.file_quit, accelerator="Alt+F4")
        self.menubar.add_cascade(label="File", underline=0, menu=filemenu)
        root.config(menu=self.menubar)
```

2.New File

```
    def file_new(self, event=None):
        result = self.save_if_modified()
        if result != None:  # None => Aborted or Save cancelled, False => Discarded, True = Saved or Not modified
            self.editor.delete(1.0, "end")
            self.editor.edit_modified(False)
            self.editor.edit_reset()
            self.file_path = None
            self.set_title()
```

3.Binding Shortcuts

```
    def main(self, event=None):
        self.editor.bind("<Control-o>", self.file_open)
        self.editor.bind("<Control-O>", self.file_open)
        self.editor.bind("<Control-S>", self.file_save)
        self.editor.bind("<Control-s>", self.file_save)
        self.editor.bind("<Control-y>", self.redo)
        self.editor.bind("<Control-Y>", self.redo)
        self.editor.bind("<Control-Z>", self.undo)
        self.editor.bind("<Control-z>", self.undo)
```

## Screenshots

![img](https://github.com/bitsplease98/Scratch-Pad/blob/master/Capture.PNG)

![img](https://github.com/bitsplease98/Scratch-Pad/blob/master/Capture1.PNG)

![img](https://github.com/bitsplease98/Scratch-Pad/blob/master/Capture3.png)
