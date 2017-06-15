# Uncomment this line to define a global platform for your project
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '9.0'
# Uncomment this line if you're using Swift
use_frameworks!

abstract_target 'qvc' do
    pod 'Alamofire'
    target 'qvclogin' do
        xcodeproj 'QvcModul/qvclogin/qvclogin.xcodeproj'
        workspace 'QvcModul/qvclogin/qvclogin.xcworkspace'

        target 'qvcloginTests' do
            inherit! :search_paths
            # Pods for testing
        end

    end

    target 'qvcprofile' do
        xcodeproj 'QvcModul/qvcprofile/qvcprofile.xcodeproj' 
        workspace 'QvcModul/qvcprofile/qvcprofile.xcworkspace'

        target 'qvcprofileTests' do
            inherit! :search_paths
            # Pods for testing
        end
    end

    post_install do |installer|
        installer.pods_project.build_configuration_list.build_configurations.each do |configuration|
                configuration.build_settings['CLANG_ALLOW_NON_MODULAR_INCLUDES_IN_FRAMEWORK_MODULES'] = 'YES'
        end
        installer.pods_project.targets.each do |target|
                target.build_configurations.each do |config|
                    config.build_settings['SWIFT_VERSION'] = '3.0'
                end
        end
    end
end

