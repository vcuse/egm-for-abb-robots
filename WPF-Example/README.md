#  Using Windows Presentation Foundation (WPF) to control ABB robots
_Last update: 10/13/2022_

![Screenshot - WPF Application](https://github.com/vcuse/egm-for-abb-robots/blob/main/Images/Screenshot-WPF-Application.jpg?raw=true)
**Image Description:** Screenshot of this WPF application running. The application contains an interface to translate and rotate a robot over its tool center point. On the background, a GoFa running EGM code is connected to the computer through the network. The GoFa is being manipulate by the WPF application.

### :warning: Warning 
The organization and authors of this repository are not liable for any consequential damage or injury that any code or information available in this repository may produce to you or others. The code available in this repository should be used only for reading purposes as different robots and settings may act different during  program execution. Use the code and information available here at your own risk, and always make sure you are following all the safety procedures recommended by your robot manufacturer. Robots can be dangerous if used inappropriately, be careful!

## Requirements
To make this application work you will need:
- Visual Studio
- .NET Core 3.1
- Windows acting as your operating system
- An ABB robot controller running EGM to serve as your EGM client

## How to run this application?
Open this project using Visual Studio by clicking on the [WPFProject.sln](https://github.com/vcuse/egm-for-abb-robots/blob/main/WPF-Example/WPFProject.sln) executable. Click on the play button on Visual Studio to execute the project. A desktop application will be opened on your computer. Use the directional buttons to control the robot.

If your virtual controller is not running EGM already, please refer to our [tutorial](https://github.com/vcuse/egm-for-abb-robots/blob/main/EGM-Preparing-your-robot.pdf) on how to setup your ABB robot for EGM communication.

## What files in this project are related to EGM?
There are only two files in this project that you should care about if you want to learn more about EGM:
- [MainWindow.xaml.cs](https://github.com/vcuse/egm-for-abb-robots/blob/main/WPF-Example/MainWindow.xaml.cs) This desktop application has only one interface, and is in the C# file associated with this interface (MainWindow.xaml) that we run the EGM communication between our computer and the ABB robot. This is the most important file as it contains the entire implementation made for this project.
- [Egm.cs](https://github.com/vcuse/egm-for-abb-robots/blob/main/WPF-Example/Egm.cs) This file contains the Abb.Egm library used in [MainWindow.xaml.cs](https://github.com/vcuse/egm-for-abb-robots/blob/main/WPF-Example/MainWindow.xaml.cs) to write messages in EGM format. Notice that this file is generated automatically. To create your own version of this file, refer to the EGM manual provided by ABB (Section 3.2 - Building an EGM sensor communication endpoint).

## Notes from the author
If you plan to create your own WPF application, don't forget to install Google.Protobuf and Google.Protobuf.Tools in the NuGet Package Manager. ABB updates EGM in almost every RobotWare update, so please use this project as a reference but be aware that newer implementations might differ from it (for better).

## Need help?
If your question is related to the information contained in this repository, feel free to [open a new issue](https://github.com/vcuse/egm-for-abb-robots/issues).
