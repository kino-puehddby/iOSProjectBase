platform :ios, '14.0'

def ignore_pods_warnings
  # ignore all warnings from all pods
  inhibit_all_warnings!
end

def install_pods
  # Code Check
  pod 'SwiftLint'

  # Resource
  pod 'SwiftGen'
end

target 'iOSProjectBase' do
  use_frameworks!
  install_pods
  ignore_pods_warnings

  target 'iOSProjectBaseTests' do
    inherit! :search_paths
    # Pods for testing
  end

  target 'iOSProjectBaseUITests' do
    # Pods for testing
  end
end

post_install do | installer |
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '9.0'
    end
  end
end
