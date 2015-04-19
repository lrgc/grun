gRun is a GTK based Run dialog that closely resembles the Windows Run dialog, just like xexec. It has a intelligent history mechanism and a dual level fork() mechanism for launching the application in its own process. gRun also has support for launching console mode application in an XTerm as well as associations for file types.

gRun is much more powerful than xexec, looks a lot better, and has the big advantage that you can start typing a command without having to mouse-click into the text field.

gRun is especially useful if you do not use the GNOME desktop which has a built-in run command, and if you use a window-manager (e.g. IceWM) where you can define a keyboard shortcut (e.g. Alt-F2) for staring gRun.

In order to compile gRun, you need to have installed a C compiler (gcc 4.3 is the currently tested one) and GTK+, version 2.10 or above, including its developement headers.