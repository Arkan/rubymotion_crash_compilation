# -*- coding: utf-8 -*-
$:.unshift("/Library/RubyMotion/lib")
require 'motion/project/template/ios'
require "rubygems"
require 'bundler'
Bundler.require
require 'bubble-wrap/all'
require "sugarcube-repl"

Motion::Project::App.setup do |app|
  app.name = 'Crash'
  app.device_family = [:iphone, :ipad]
  app.deployment_target = "6.0"
  # app.sdk_version = "6.1"
  app.sdk_version = "7.0"

  app.pods do
    pod 'Reachability'
    pod 'SVProgressHUD', '0.9'
    pod 'DACircularProgress', '~> 2.1.0'
    pod 'MagicalRecord', '2.1'
    pod 'AFNetworking', "1.3.2"
    pod 'MessagePack', :git => 'git@github.com:Arkan/msgpack-objectivec.git' #:podspec => '/Users/florian/.cocoapods/AkMessagePack/AkMessagePack.podspec'
    pod 'BCGenieEffect', '~> 1.0'
    pod 'SDWebImage', '~> 3.3'
    pod 'UIActivityIndicator-for-SDWebImage'
    pod 'NSData+MD5Digest'
    pod "Godzippa"
    pod 'NSLogger'
  end

  app.development do
    app.codesign_certificate = "iPhone Developer: Florian Bertholin"
    app.provisioning_profile = "/Users/florian/Library/MobileDevice/Provisioning\ Profiles/9D68FEA4-105F-4B89-9BFE-8B396B4B94BD.mobileprovision"
    app.entitlements['aps-environment'] = 'development'
    app.entitlements['get-task-allow']  = true
    app.testflight do
      app.testflight.sdk = 'vendor/TestFlightSDK'
      app.testflight.api_token = '??'
      app.testflight.team_token = '??'
      app.testflight.app_token = "??"
      app.testflight.notify = false # default is false
      # app.testflight.identify_testers = true # default is false
      app.testflight.distribution_lists = ['list']
    end
  end

  document_types = [
    {
      'CFBundleTypeName'        => 'Picture File',
      'LSHandlerRank'           => 'Default',
      'CFBundleTypeRole'        => 'Viewer',
      'LSItemContentTypes'      => ['public.image'],
      'CFBundleTypeIconFiles'   => ['icon_iphone.png']
    }
  ]
  app.info_plist["CFBundleDocumentTypes"] = document_types
  app.redgreen_style = :full  # :focused, :full
end

if File.exists?('devices.yml')
  namespace :device do
    devices = YAML.load(File.read('devices.yml'))
    devices.each do |name, id|
      desc "Deploy on #{name}"
      task name do
        sh "rake device id=#{id}"
      end
    end
    devices_name = devices.collect{|name,id| name}
    desc "Deploy on all devices(#{devices_name.join(', ')})"
    task "all" do
      devices_name.each do |d|
        sh "rake device:#{d}"
      end
    end
  end
end