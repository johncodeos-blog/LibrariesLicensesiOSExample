# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'LibrariesLicensesExample' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!
  pod 'Alamofire'
  pod 'FLAnimatedImage'
  pod 'SDWebImage'

  # Pods for LibrariesLicensesExample

end

post_install do | installer |
  require 'fileutils'
  FileUtils.cp_r('Pods/Target Support Files/Pods-LibrariesLicensesExample/Pods-LibrariesLicensesExample-acknowledgements.plist', 'Resources/Settings.bundle/Acknowledgements.plist', :remove_destination => true)
  installer.aggregate_targets.each do |aggregate_target|
    aggregate_target.xcconfigs.each do |config_name, config_file|
      xcconfig_path = aggregate_target.xcconfig_path(config_name)
      config_file.save_as(xcconfig_path)
    end
  end
end