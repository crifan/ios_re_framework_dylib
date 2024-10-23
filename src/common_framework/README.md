# 常见Frameworks框架

常见Frameworks：（以`iOS 4.0 (8A293)`为例）

| Frameworks | 包名 | （内部函数的）前缀 | 描述 |
| ---------- | ---- | -------------- | ----|
| aaaaaaaaaa | aaaa | aaaaaa | aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa |
| Accelerate.framework | com.apple.Accelerate | cblas, vDSP | Vector and Matrix math, digital signal processing, large number handling, and image processing |
| AddressBook.framework | com.apple.AddressBook | AB | Provides access to the Address Book database |
| AddressBookUI.framework | com.apple.AddressBookUI | | |
| AssetsLibrary.framework | com.yourcompany.AssetsLibrary | AL | Used to access pictures and videos managed by the Photos application |
| AudioToolbox.framework | com.apple.audio.toolbox.AudioToolbox | AU, Audio | Provides interfaces for recording, playback, stream parsing, and managing audio sessions. Part of CoreAudio |
| AudioUnit.framework | com.apple.audio.units.AudioUnit |AU, Audio | Interfaces for the loading of audio units and their use|
| AVFoundation.framework | com.apple.avfoundation | AV| Used for playing and recording audio and video|
| CFNetwork.framework | com.apple.CFNetwork |CF | Interfaces for high-performance networking |
| CoreAudio.framework | com.apple.audio.CoreAudio |Audio | Declares constants and data-types used by other interfaces in CoreAudio|
| CoreData.framework | com.apple.CoreData |NS |Interfaces for application data model manipulation |
| CoreFoundation.framework | com.apple.CoreFoundation | CF | Basic data management and services|
| CoreGraphics.framework | |CG |APIs to interface with the Quartz engine, allows 2D rendering, etc |
| CoreLocation.framework | com.apple.corelocation |CL | Interfaces for determining location|
| CoreMedia.framework | com.apple.CoreMedia |CM |Low-level routines for manipulating audio and video |
| CoreMotion.framework | com.apple.coremotion | CM| Interfaces for accessing accelerometer and gyrometric data|
| CorePDF.framework | com.apple.CorePDF | | |
| CoreTelephony.framework | com.apple.coretelephony | CT| Allows access to Carrier information and information pertaining to a current call|
| CoreText.framework | com.apple.CoreText |CT | Text layout and rendering engine|
| CoreVideo.framework | com.apple.CoreVideo |CV | Low-level routines for manipulating audio and video - Apple advises not to use this framework directly, and although public doesn't document much of it|
| EventKit.framework | com.apple.eventkit |EK | Interfaces for accessing Calendar event data. This is a replacement for the older Calendar.framework|
| EventKitUI.framework | com.apple.eventkitui | | |
| ExternalAccessory.framework | com.apple.ExternalAccessory |EA |Interfaces for communication with attached external accessories via 30-pin dock or Bluetooth. Lightning is not yet mentioned by Apple in documentation |
| Foundation.framework | com.apple.Foundation | NS|Objective-C wrappers to features found in CoreFoundation with extra features and functionality not covered by Objective-C |
| GameKit.framework | com.apple.GameKit | GK| Manages P2P connectivity. With iOS 4.1 and later, GameKit can be used with Game Center (an extension to the framework) to create social games|
| iAd.framework | com.apple.iAd | AD| |
| IOKit.framework | | | Low-level framework for communicating with the kernel and hardware. Apple advises not to use this framework directly and will reject it from the App Store|
| ImageIO.framework | com.apple.ImageIO.framework |CG | Input and output for images. Part of CoreGraphics|
| MapKit.framework | com.apple.MapKit |MK |Classes for embedding Map graphical interfaces. Before iOS 5.1, Google Mobile Maps was used to provide map data; afterwards, Apple provided the map data. |
| MediaPlayer.framework | com.apple.MediaPlayer | MP | Provides facilities to play audio, and video. Also allows access to the iPod or Music library. |
| MessageUI.framework | com.apple.messageui | MF | Interfaces for SMS and Mail compose view controllers without leaving the application. |
| MobileCoreServices.framework | com.apple.MobileCoreServices | UT | Defines UTIs supported by the system |
| OpenAL.framework | com.apple.audio.OpenAL | AL | Interface for the cross-platform audio library |
| OpenGLES.framework | com.apple.opengles | EAGL, GL  | Interface for the OpenGL ES library |
| QuartzCore.framework | com.apple.QuartzCore | CA | Contains the CoreAnimation interfaces |
| QuickLook.framework | com.apple.QuickLook | QL | interfaces for previewing files of unknown formats |
| Security.framework | com.apple.Security | CSSM, Sec | Interfaces for managing keys, trust policies, and certificates |
| StoreKit.framework | com.apple.StoreKit | SK | Interfaces for handling in-app purchase transactions |
| System.framework |  |  |  |
| SystemConfiguration.framework | com.apple.SystemConfiguration | SC | Interfaces for determining network availability |
| UIKit.framework | com.apple.UIKit | UI | Classes for iOS UI elements and for the user interface layer of applications |
