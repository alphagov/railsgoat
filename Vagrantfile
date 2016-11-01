VAGRANTFILE_API_VERSION = "2"
ENV['VAGRANT_DEFAULT_PROVIDER'] ||= 'virtualbox'
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.network "forwarded_port", guest: 3000, host: 3000

  config.vm.define "railsgoat" do |rg|
    rg.vm.box = 'railsgoat'
    rg.vm.box_url = 'https://s3-eu-west-1.amazonaws.com/govuk-2016-06-13-security-workshop/govuk-2016-11-04-security-workshop.box'
  end

end


# To run the app in the vagrant box:
#
# vagrant ssh
# cd /vagrant
# bundle exec rails server -b 0.0.0.0
#
# Then you'll be able to see the app at localhost:3000 in your browser.
