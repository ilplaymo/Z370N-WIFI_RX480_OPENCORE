<!DOCTYPE html>
<html>
    <head>
     <meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="stylesheet" href="github-markdown.css">
        <meta charset="utf-8"/>
        <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
        <meta name="description" content=""/>
        <meta name="author" content=""/>
        <link href="css/style.css" rel="stylesheet"/>
        <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Manrope&display=swap"/>
    </head>
    <body style="font-family: 'Manrope', sans-serif;">
        <h2>HackOS</h2>
        <hr/>
        <p>My Desktop Hackintosh</p>
        <p>made using:</p>
         <h3 style="font-weight: bold; font-size: 18px;"><strong>
			Gigabyte z370n-WiFi (Bios F14 with patched CFG-lock)<br/>
			AMD Radeon RX480 8GB<br/>
          Broadcom BCM4360 </strong></p>
        <p>OpenCore 0.7.7</p></h3>
        <p>EFI updated JAN 12 2022</p>
 <hr>
        <p>System Info:</p>
        <table>
            <tbody>
                <tr>
                    <td>Host</td>
                    <td>HackOS</td>
                </tr>
                <tr>
                    <td>OS</td>
                    <td>macOS Monterey Version 12.0.1 (Build 21A559)</td>
                </tr>
                <tr>
                    <td>RAM</td>
                    <td>16GB</td>
                </tr>
                <tr>
                    <td>Model Identifier</td>
                    <td>iMac19,1</td>
                </tr>
                <tr>
                    <td>Model</td>
                    <td>iMac (Retina 5K, 27-inch, 2019)</td>
                </tr>
                <tr>
                    <td>Platform ID</td>
                    <td>0x3E920003</td>
                </tr>
                <tr>
                    <td>VDA Decoder</td>
                    <td>Fully Supported</td>
                </tr>
                <tr>
                    <td>VDA Decoder</td>
                    <td>Intel CoffeeLake-S GT2 [UHD Graphics 630]</td>
                </tr>
                <tr>
                    <td>GPU Device ID</td>
                    <td>0x3E928086</td>
                </tr>
                <tr>
                    <td>dGPU Name</td>
                    <td>AMD Radeon RX 480</td>
                </tr>
                <tr>
                    <td>Metal Supported</td>
                    <td>Yes</td>
                </tr>
                <tr>
                    <td>WiFi Device</td>
                    <td>Broadcom BCM4360 802.11ac</td>
                </tr>
                <tr>
                    <td>BT Device (part of BCM4360)</td>
                    <td>Broadcom BCM2046B1</td>
                </tr>
                <tr>
                    <td>Audio Device</td>
                    <td>Realtek ALC1220</td>
                </tr>
                <tr>
                    <td>Audio Layout ID</td>
                    <td>7</td>
                </tr>
            </tbody>
        </table>
    </div>
    <hr>
  <h3>BIOS SETTINGS:</h3>
  <ul dir="auto">
  <li><strong>Load optimised defaults</strong></li>
  <li>MIT &gt; Advanced Memory Settings &gt; XMP &gt; <strong>Profile 1</strong></li>
  <li>MIT &gt; Advanced CPU Core Settings &gt; Enhanced Multi-core Performance &gt; <strong>ENABLED</strong></li>
  <li>SmartFan &gt; Fan Control Mode &gt; <strong>PWM</strong></li>
  <li>SmartFan &gt; Auto Stop &gt; <strong>ENABLED</strong></li>
  <li>BIOS &gt; FastBoot &gt; <strong>DISABLED</strong></li>
  <li>BIOS &gt; CSM Support &gt; <strong>DISABLED</strong></li>
  <li>BIOS &gt; Windows 8/10 Features &gt; <strong>Windows 8/10 WHQL</strong></li>
  <li>BIOS &gt; Secure Boot &gt; <strong>DISABLED</strong></li>
  <li>Peripherals &gt; Above 4G Decoding &gt; <strong>ENABLED</strong></li>
  <li>Peripherals &gt; Re-Size Bar &gt; <strong>DISABLED</strong></li>
  <li>Peripherals &gt; Intel PTT &gt; <strong>DISABLED</strong></li>
  <li>Peripherals &gt; SGX &gt; <strong>DISABLED</strong></li>
  <li>Peripherals &gt; Trusted Computing &gt; <strong>DISABLED</strong></li>
  <li>Peripherals &gt; SATA and RST Configuration &gt; SATA Mode Selection &gt; <strong>AHCI</strong></li>
  <li>Peripherals &gt; SATA and RST Configuration &gt; Aggressive LPM Support &gt; <strong>DISABLED</strong></li>
  <li>Peripherals &gt; USB Config &gt; Legacy &gt; <strong>DISABLED</strong></li> 
  <li>Peripherals &gt; USB Config &gt; XHCI Handoff &gt; <strong>ENABLED</strong></li>
  <li>Peripherals &gt; USB Config &gt; Port 60/64 emulation &gt; <strong>DISABLED</strong></li>
  <li>Chipset &gt; VT-d &gt; <strong>DISABLED</strong></li>
  <li>Chipset &gt; Internal Graphics &gt; <strong>ENABLED</strong> with <strong>64MB</strong> min and <strong>128MB</strong> max;</li>
  <li>Chipset &gt; Wake On Lan &gt; <strong>DISABLED</strong> <em>(remind to disable it on adapters too)</em></li>
  <li>Power &gt; ErP &gt; <strong>ENABLED</strong></li>
  <li>Power &gt; Power Loading &gt; <strong>DISABLED</strong></li>
  <li>Save and restart</li>
  </ul>  
  <hr>
  <p><strong>in this Repo you can download a perfect working EFI plus the BIOS rel. F14 profile</strong></p>
  <p>to fix the missing CFG-lock you should do:
  <ul> 
  <li>Mount the <strong>EFI partition</strong> of the <strong>USB</strong> disk using <a href="https://github.com/corpnewt/MountEFI">MountEFI</a> utility and      <strong>copy the EFI folder</strong> inside <strong><code>/Volumes/EFI</code></strong></li>
  <li><strong>Boot</strong> the target machine with <strong>USB</strong> disk you just made</li>
  <li>Using <strong>Modified GRUB Shell</strong> we must disable <strong>CFG Lock</strong> first with command below:</li>
  </ul> 
  <pre>setup_var_3 0x5A4 0x00</pre>
  </p>
  <hr>
  <p><strong>the Operating System boot time is around 7 seconds, time calculated from the choice of boot options to the entry of the user password<strong></p>
  </body>
  </html>
