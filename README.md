## To reproduce the issue

```
➜  crash_motion git:(master) ✗ motion -v
2.7
➜  crash_motion git:(master) ✗ rake
================================================================================
Your maintenance plan is about to expire in 36 days. Run `motion account' to renew it.
================================================================================

     Build ./build/iPhoneSimulator-6.0-Development
     Build vendor/Pods
Build settings from command line:
    ARCHS = i386
    CONFIGURATION_BUILD_DIR = /Users/florian/tmp/crash_motion/vendor/Pods/.build
    IPHONEOS_DEPLOYMENT_TARGET = 6.0
    SDKROOT = iphonesimulator7.0

=== BUILD TARGET Pods OF PROJECT Pods WITH CONFIGURATION Release ===

Check dependencies
warning: CODE_SIGN_ENTITLEMENTS specified without a valid Developer Signing Identity for iOS: (null)

Libtool .build/libPods.a normal i386
    cd /Users/florian/tmp/crash_motion/vendor/Pods
    setenv IPHONEOS_DEPLOYMENT_TARGET 6.0
    setenv PATH "/Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin:/Applications/Xcode5-DP4.app/Contents/Developer/usr/bin:/Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bin:/Users/florian/.rbenv/versions/2.0.0-p247/bin:/usr/local/Cellar/rbenv/0.4.0/libexec:/Users/florian/.rbenv/shims:/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/X11/bin:/Users/florian/Codes/deployment_recipes/scripts:/usr/local/share/python"
    /Applications/Xcode5-DP4.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool -static -arch_only i386 -syslibroot /Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk -L/Users/florian/tmp/crash_motion/vendor/Pods/.build -filelist /Users/florian/tmp/crash_motion/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods.build/Objects-normal/i386/Pods.LinkFileList -framework Foundation -o /Users/florian/tmp/crash_motion/vendor/Pods/.build/libPods.a
/Applications/Xcode5-DP4.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: file: /Users/florian/tmp/crash_motion/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods.build/Objects-normal/i386/UIImage+WebP.o has no symbols

** BUILD SUCCEEDED **

   Compile ./app/app_delegate.rb
      Link ./build/iPhoneSimulator-6.0-Development/Crash.app/Crash
    Create ./build/iPhoneSimulator-6.0-Development/Crash.app/Info.plist
    Create ./build/iPhoneSimulator-6.0-Development/Crash.app/PkgInfo
      Copy vendor/Pods/Resources/SVProgressHUD.bundle/error.png
      Copy vendor/Pods/Resources/SVProgressHUD.bundle/error@2x.png
      Copy vendor/Pods/Resources/SVProgressHUD.bundle/success.png
      Copy vendor/Pods/Resources/SVProgressHUD.bundle/success@2x.png
    Create ./build/iPhoneSimulator-6.0-Development/Crash.dSYM
  Simulate ./build/iPhoneSimulator-6.0-Development/Crash.app
2013-08-29 15:29:09.345 Crash[19071:a0b] Cannot find executable for CFBundle 0xe1b87f0 </Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk/System/Library/AccessibilityBundles/MusicLibrary.axbundle> (not loaded)
2013-08-29 15:29:09.362 Crash[19071:a0b] Cannot find executable for CFBundle 0xce01950 </Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk/System/Library/AccessibilityBundles/GeoServices.axbundle> (not loaded)
2013-08-29 15:29:09.370 Crash[19071:a0b] Cannot find executable for CFBundle 0xe37f390 </Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk/System/Library/AccessibilityBundles/CertUIFramework.axbundle> (not loaded)
(main)> Main !!!!!
(main)> rake aborted!

/Library/RubyMotion/lib/motion/project/template/ios.rb:113:in `initialize'
/Library/RubyMotion/lib/motion/project/template/ios.rb:113:in `initialize'
/Library/RubyMotion/lib/motion/project/template/ios.rb:113:in `new'
/Library/RubyMotion/lib/motion/project/template/ios.rb:113:in `system'
/Library/RubyMotion/lib/motion/project/template/ios.rb:113:in `block in <top (required)>'
Tasks: TOP => default => simulator
(See full trace by running task with --trace)

WARNING: Automatic dependency detection does not work with motion-support. Turn it off in your Rakefile:

  app.detect_dependencies = false

➜  crash_motion git:(master) ✗ bundle update ProMotion
Updating git@github.com:clearsightstudio/ProMotion.git
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/..
Resolving dependencies...
Using rake (10.0.4)
Using ProMotion (1.0.3) from git@github.com:clearsightstudio/ProMotion.git (at master)
Using i18n (0.6.5)
Using multi_json (1.7.9)
Using activesupport (3.2.14)
Using addressable (2.3.5)
Using awesome_print_motion (0.1.0)
Using bubble-wrap (1.3.0)
Using claide (0.2.0)
Using multipart-post (1.2.0)
Using faraday (0.8.8)
Using faraday_middleware (0.9.0)
Using hashie (2.0.5)
Using netrc (0.7.7)
Using octokit (1.25.0)
Using cocoapods-core (0.18.1)
Using cocoapods-downloader (0.1.2)
Using colored (1.2)
Using escape (0.0.4)
Using json (1.7.7)
Using open4 (1.3.0)
Using xcodeproj (0.5.5)
Using cocoapods (0.18.1)
Using motion-require (0.0.6)
Using formotion (1.4.0)
Using geomotion (0.12.1)
Using mini_portile (0.5.1)
Using motion-cocoapods (1.3.5)
Using motion-redgreen (0.1.0)
Using motion-support (0.2.4)
Using motion-testflight (1.5)
Using nokogiri (1.6.0)
Using motion_migrate (0.1.0)
Using sugarcube (0.20.23)
Using teacup (2.0.5)
Using bundler (1.3.5)
Your bundle is updated!
➜  crash_motion git:(master) ✗ rake
================================================================================
Your maintenance plan is about to expire in 36 days. Run `motion account' to renew it.
================================================================================

     Build ./build/iPhoneSimulator-6.0-Development
     Build vendor/Pods
Build settings from command line:
    ARCHS = i386
    CONFIGURATION_BUILD_DIR = /Users/florian/tmp/crash_motion/vendor/Pods/.build
    IPHONEOS_DEPLOYMENT_TARGET = 6.0
    SDKROOT = iphonesimulator7.0

=== BUILD TARGET Pods OF PROJECT Pods WITH CONFIGURATION Release ===

Check dependencies
warning: CODE_SIGN_ENTITLEMENTS specified without a valid Developer Signing Identity for iOS: (null)

Libtool .build/libPods.a normal i386
    cd /Users/florian/tmp/crash_motion/vendor/Pods
    setenv IPHONEOS_DEPLOYMENT_TARGET 6.0
    setenv PATH "/Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin:/Applications/Xcode5-DP4.app/Contents/Developer/usr/bin:/Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bin:/Users/florian/.rbenv/versions/2.0.0-p247/bin:/usr/local/Cellar/rbenv/0.4.0/libexec:/Users/florian/.rbenv/shims:/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/X11/bin:/Users/florian/Codes/deployment_recipes/scripts:/usr/local/share/python"
    /Applications/Xcode5-DP4.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool -static -arch_only i386 -syslibroot /Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk -L/Users/florian/tmp/crash_motion/vendor/Pods/.build -filelist /Users/florian/tmp/crash_motion/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods.build/Objects-normal/i386/Pods.LinkFileList -framework Foundation -o /Users/florian/tmp/crash_motion/vendor/Pods/.build/libPods.a
/Applications/Xcode5-DP4.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: file: /Users/florian/tmp/crash_motion/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods.build/Objects-normal/i386/UIImage+WebP.o has no symbols

** BUILD SUCCEEDED **

   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/cocoatouch/table_view_cell.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/containers/split_screen.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/logger.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/containers/tabs.rb
2013-08-29 15:29:51.450 ruby[19519:f0f] unrecognized runtime type `{_opaque_pthread_mutex_t=l[40c]}' (TypeError)
2013-08-29 15:29:51.453 ruby[19519:f0f] *** Terminating app due to uncaught exception 'TypeError', reason: 'unrecognized runtime type `{_opaque_pthread_mutex_t=l[40c]}' (TypeError)
'
*** Call stack at first throw:
(
	0   CoreFoundation                      0x9552be8b __raiseError + 219
	1   libobjc.A.dylib                     0x967fa52e objc_exception_throw + 230
	2   ruby                                0x0013a419 rb_rescue2 + 793
	3   ruby                                0x0013a4c7 rb_vm_raise + 167
	4   ruby                                0x0002c9f1 rb_exc_raise + 17
	5   ruby                                0x0002ae0f rb_raise + 127
	6   ruby                                0x000fbd16 _ZN13RoxorCompiler12convert_typeEPKc + 892
	7   ruby                                0x00161ec6 _ZN16RoxorAOTCompiler24compile_static_bs_boxedsEv + 394
	8   ruby                                0x001651e6 _ZN16RoxorAOTCompiler23compile_static_bs_filesEv + 176
	9   ruby                                0x0010bdf8 _ZN16RoxorAOTCompiler21compile_init_functionERSt6vectorIPN4llvm8FunctionESaIS3_EE + 6324
	10  ruby                                0x0013f78b rb_vm_aot_compile + 427
	11  ruby                                0x00099368 ruby_process_options + 440
	12  ruby                                0x000df24c main + 140
	13  ruby                                0x00002135 start + 53
)
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/cocoatouch/view_controller.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/delegate/delegate_parent.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/delegate/delegate_module.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/delegate/delegate_notifications.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/map/map_screen_module.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/map/map_screen_annotation.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/web/web_screen_module.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/screen/screen_module.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/map/map_screen.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/table/extensions/indexable.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/screen/screen.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/table/grouped_table.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/table/extensions/refreshable.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/pro_motion.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/table/table_screen.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/table/extensions/searchable.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/table/table.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/thirdparty/formotion_screen.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/table/grouped_table_screen.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/delegate/delegate.rb
   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/web/web_screen.rb
rake aborted!
Command failed with status (): [/usr/bin/env VM_KERNEL_PATH="/Library/Ruby...]
/Library/RubyMotion/lib/motion/project/builder.rb:118:in `block (2 levels) in build'
/Library/RubyMotion/lib/motion/project/builder.rb:110:in `each'
/Library/RubyMotion/lib/motion/project/builder.rb:110:in `block in build'
/Library/RubyMotion/lib/motion/project/builder.rb:481:in `call'
/Library/RubyMotion/lib/motion/project/builder.rb:481:in `block (2 levels) in initialize'
Tasks: TOP => build:simulator
(See full trace by running task with --trace)

WARNING: Automatic dependency detection does not work with motion-support. Turn it off in your Rakefile:

  app.detect_dependencies = false

➜  crash_motion git:(master) ✗ rake
================================================================================
Your maintenance plan is about to expire in 36 days. Run `motion account' to renew it.
================================================================================

     Build ./build/iPhoneSimulator-6.0-Development
     Build vendor/Pods
Build settings from command line:
    ARCHS = i386
    CONFIGURATION_BUILD_DIR = /Users/florian/tmp/crash_motion/vendor/Pods/.build
    IPHONEOS_DEPLOYMENT_TARGET = 6.0
    SDKROOT = iphonesimulator7.0

=== BUILD TARGET Pods OF PROJECT Pods WITH CONFIGURATION Release ===

Check dependencies
warning: CODE_SIGN_ENTITLEMENTS specified without a valid Developer Signing Identity for iOS: (null)

Libtool .build/libPods.a normal i386
    cd /Users/florian/tmp/crash_motion/vendor/Pods
    setenv IPHONEOS_DEPLOYMENT_TARGET 6.0
    setenv PATH "/Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin:/Applications/Xcode5-DP4.app/Contents/Developer/usr/bin:/Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bin:/Users/florian/.rbenv/versions/2.0.0-p247/bin:/usr/local/Cellar/rbenv/0.4.0/libexec:/Users/florian/.rbenv/shims:/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/X11/bin:/Users/florian/Codes/deployment_recipes/scripts:/usr/local/share/python"
    /Applications/Xcode5-DP4.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool -static -arch_only i386 -syslibroot /Applications/Xcode5-DP4.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk -L/Users/florian/tmp/crash_motion/vendor/Pods/.build -filelist /Users/florian/tmp/crash_motion/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods.build/Objects-normal/i386/Pods.LinkFileList -framework Foundation -o /Users/florian/tmp/crash_motion/vendor/Pods/.build/libPods.a
/Applications/Xcode5-DP4.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: file: /Users/florian/tmp/crash_motion/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods.build/Objects-normal/i386/UIImage+WebP.o has no symbols

** BUILD SUCCEEDED **

   Compile /Users/florian/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0/bundler/gems/ProMotion-36b8ff860d69/lib/ProMotion/logger.rb
2013-08-29 15:30:44.659 ruby[20369:f0f] unrecognized runtime type `{_opaque_pthread_mutex_t=l[40c]}' (TypeError)
2013-08-29 15:30:44.660 ruby[20369:f0f] *** Terminating app due to uncaught exception 'TypeError', reason: 'unrecognized runtime type `{_opaque_pthread_mutex_t=l[40c]}' (TypeError)
'
*** Call stack at first throw:
(
	0   CoreFoundation                      0x9552be8b __raiseError + 219
	1   libobjc.A.dylib                     0x967fa52e objc_exception_throw + 230
	2   ruby                                0x0013a419 rb_rescue2 + 793
	3   ruby                                0x0013a4c7 rb_vm_raise + 167
	4   ruby                                0x0002c9f1 rb_exc_raise + 17
	5   ruby                                0x0002ae0f rb_raise + 127
	6   ruby                                0x000fbd16 _ZN13RoxorCompiler12convert_typeEPKc + 892
	7   ruby                                0x00161ec6 _ZN16RoxorAOTCompiler24compile_static_bs_boxedsEv + 394
	8   ruby                                0x001651e6 _ZN16RoxorAOTCompiler23compile_static_bs_filesEv + 176
	9   ruby                                0x0010bdf8 _ZN16RoxorAOTCompiler21compile_init_functionERSt6vectorIPN4llvm8FunctionESaIS3_EE + 6324
	10  ruby                                0x0013f78b rb_vm_aot_compile + 427
	11  ruby                                0x00099368 ruby_process_options + 440
	12  ruby                                0x000df24c main + 140
	13  ruby                                0x00002135 start + 53
)
rake aborted!
Command failed with status (): [/usr/bin/env VM_KERNEL_PATH="/Library/Ruby...]
/Library/RubyMotion/lib/motion/project/builder.rb:118:in `block (2 levels) in build'
/Library/RubyMotion/lib/motion/project/builder.rb:110:in `each'
/Library/RubyMotion/lib/motion/project/builder.rb:110:in `block in build'
/Library/RubyMotion/lib/motion/project/builder.rb:481:in `call'
/Library/RubyMotion/lib/motion/project/builder.rb:481:in `block (2 levels) in initialize'
Tasks: TOP => build:simulator
(See full trace by running task with --trace)
```