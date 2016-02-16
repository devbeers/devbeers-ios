xcodeproj 'Devbeers/Devbeers.xcodeproj'
platform :ios, '8.0'
use_frameworks!

def common_pods
    pod 'RxSwift', '~> 2.2.0'
    pod 'RxCocoa', '~> 2.2.0'
end

def test_pods
    pod 'RxBlocking', '~> 2.2.0'
    pod 'RxTests', '~> 2.2.0'
end

target :Devbeers do
    common_pods
end

target :DevbeersTests do
    common_pods
    test_pods
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['ENABLE_TESTABILITY'] = 'YES'
            config.build_settings['ONLY_ACTIVE_ARCH'] = 'NO'
        end
    end
end
