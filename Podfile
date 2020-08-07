using_local_pods = ENV['USE_LOCAL_PODS'] == 'true' || false

platform :ios, '11.0'

if using_local_pods
  # Pull pods from sibling directories if using local pods
  target 'EosioSwiftSoftkeySignatureProvider' do
    use_frameworks!

    pod 'EosioSwift', :path => '../eosio-swift'
    pod 'EosioSwiftEcc', :path => '../eosio-swift-ecc'
    pod 'SwiftLint'
    pod 'UIExtensions.swift', :path => '../gui-kit/'

    target 'EosioSwiftSoftkeySignatureProviderTests' do
      inherit! :search_paths
      pod 'EosioSwift', :path => '../eosio-swift'
      pod 'EosioSwiftEcc', :path => '../eosio-swift-ecc'

      pod 'UIExtensions.swift', :path => '../gui-kit/'
    end
  end
else
  # Pull pods from sources above if not using local pods
  target 'EosioSwiftSoftkeySignatureProvider' do
    use_frameworks!

    pod 'EosioSwift', git: 'https://github.com/horizontalsystems/eosio-swift'
    pod 'EosioSwiftEcc', git: 'https://github.com/horizontalsystems/eosio-swift-ecc.git'
    pod 'SwiftLint'
    pod 'UIExtensions.swift'

    target 'EosioSwiftSoftkeySignatureProviderTests' do
      inherit! :search_paths
      pod 'EosioSwift', git: 'https://github.com/horizontalsystems/eosio-swift'
      pod 'EosioSwiftEcc', git: 'https://github.com/horizontalsystems/eosio-swift-ecc.git'
    end
  end
end
