VAGRANTFILE_API_VERSION = "2"
ENV['VAGRANT_DEFAULT_PROVIDER'] ||= 'docker'
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.network "forwarded_port", guest: 3000, host: 3000

  config.vm.define "railsgoat" do |rg|
    rg.vm.box_url = 'https://s3-eu-west-1.amazonaws.com/govuk-2016-06-13-security-workshop/railsgoat.box'
  end

end

# RAILS_ENV=mysql bundle exec rails server -b 0.0.0.0
