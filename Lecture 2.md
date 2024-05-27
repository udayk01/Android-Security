### Android Debug Bridge (adb) 

It is a versatile command-line tool that lets you communicate with a device.

The adb command facilitates a variety of device actions, such as installing and debugging apps. adb provides access to a Unix shell that you can use to run a variety of commands on a device.

It is a client-server program that includes three components:

• A client, which sends commands. The client runs on your development machine. You can invoke a client from a command-line terminal by issuing an adb command.

• A daemon (adbd), which runs commands on a device. The daemon runs as a background process on each device. The daemon on the Android device connects with the server on the host PC over USB or TCP, which connects to the client that is used by the end-user over TCP.

• A server, which manages communication between the client and the daemon. The server runs as a background process on your development machine. The default port number on which the adb server runs is 5037.

ADB is included in the Android SDK Platform Tools package, which is installed at ${ANDROID_HOME}/platform-tools/.

If the Android SDK is not installed in the system, we can use the sudo apt install android-tools-adb command to install adb as a system package.

After the PATH environment variable is set appropriately, we verify the program execution by typing adb in the terminal.

![Screenshot 2024-05-27 100829](https://github.com/udayk01/Android-Security/assets/52235763/b402578b-56bb-423c-aaac-90d537fd1517)

![Screenshot 2024-05-27 100948](https://github.com/udayk01/Android-Security/assets/52235763/a1fbbd86-b131-4114-a013-dadca72cbcb0)

> Android Virtual Device (AVD) is started by typing the following command.

![Screenshot 2024-05-27 101422](https://github.com/udayk01/Android-Security/assets/52235763/fa384335-832a-4199-ab2c-ff916be75275)

![Screenshot 2024-05-27 101708](https://github.com/udayk01/Android-Security/assets/52235763/90ce52c0-1a93-4a3d-99c8-88227787a609)

### Basic ADB Commands

```adb devices```

![Screenshot 2024-05-27 102046](https://github.com/udayk01/Android-Security/assets/52235763/f29f8e34-bed4-4362-bbe7-9cc7d9c54c0e)

```adb -s emulator-5554 shell```

![image](https://github.com/udayk01/Android-Security/assets/52235763/e4ac55dd-38d2-47b8-979f-4f91270719dd)

```id```

![image](https://github.com/udayk01/Android-Security/assets/52235763/39e8b909-c796-407a-871f-3c1ec3b98912)

```ls```

![image](https://github.com/udayk01/Android-Security/assets/52235763/ed115990-8d3f-46b9-8664-79e31b1d077d)

```cd sdcard```
```ls```

![image](https://github.com/udayk01/Android-Security/assets/52235763/a620c142-92a4-4e45-b6d8-3b200f4bac46)

### pm (Package Manager) 

It is an utility program for retrieving various kinds of information related to the application packages that are currently installed on the device.

```pm list packages```

![image](https://github.com/udayk01/Android-Security/assets/52235763/4f5c6b3a-f049-49f3-84c2-9245b8655e59)

``` pm list packages | grep youtube```

![image](https://github.com/udayk01/Android-Security/assets/52235763/495634a1-d3d2-4436-9104-1b4623b82e2b)

> pm list packages has various options to configure the output. -3 option is used to filter and display only show third party packages. -s option is used to filter and display only system packages.

``` pm list packages -3```

![image](https://github.com/udayk01/Android-Security/assets/52235763/1a8112f2-18eb-40a0-a3cb-0c0dce656e2e)

> To check the Process ID (PID) of the currently running applications, we use the ps -A command.

``` ps -A | grep example ```

![image](https://github.com/udayk01/Android-Security/assets/52235763/73287e7c-a731-47b4-a8d4-d80942145476)

> pm path is used to get the path of the installed APK file.

```pm path com.example.exapp```

![image](https://github.com/udayk01/Android-Security/assets/52235763/3e6f9dae-71ec-4c66-b936-612fed832685)

```exit```

![image](https://github.com/udayk01/Android-Security/assets/52235763/2e3bb6c9-9f06-436a-94f1-7c164e53a72b)

![image](https://github.com/udayk01/Android-Security/assets/52235763/b242a76d-d782-4b72-9ac4-fef9550fbd78)

```adb pull /data/app/~~8UAxlYP3QSnP8_ixuFq8cA==/com.example.exapp-8kV48cJw7jnpMcuRekg67Q==/base.apk```

![image](https://github.com/udayk01/Android-Security/assets/52235763/eb4cba3a-3aa7-4908-879a-3af2cfafca4f)

```echo "This is some file" > somefile.txt```

![image](https://github.com/udayk01/Android-Security/assets/52235763/a8125b15-a290-4053-af90-e1e4bcc6886c)

```adb push somefile.txt /sdcard/```

![image](https://github.com/udayk01/Android-Security/assets/52235763/205ff3a5-0f16-4c2f-b46b-5b8df7e394bb)

![image](https://github.com/udayk01/Android-Security/assets/52235763/45f5a965-4bf6-47e5-a189-35f92164b9e8)

> As we can see its pushed inside.

### Find Application UID

> Method 1

21:51 Reference

![image](https://github.com/udayk01/Android-Security/assets/52235763/4c3fd496-2a28-447f-8783-fdb22b7bc92e)

> Method 2

```pm list packages -U```

![image](https://github.com/udayk01/Android-Security/assets/52235763/0be9bf58-0ba3-420c-9de5-2299e71e9c49)

 ```pm list packages -U -3```

![image](https://github.com/udayk01/Android-Security/assets/52235763/63d89c3e-902b-4fee-b1b8-e41409a026b2)
