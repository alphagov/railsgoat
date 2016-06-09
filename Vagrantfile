$script = <<SCRIPT
sudo debconf-set-selections <<< 'mysql-server mysql-server/root_password password root_password'
sudo debconf-set-selections <<< 'mysql-server mysql-server/root_password_again password root_password'


sudo apt-get update
sudo apt-get install -y git
sudo apt-get install -y libssl-dev libreadline-dev zlib1g-dev
sudo apt-get install -y mysql-server libmysqlclient-dev libsqlite3-dev
sudo apt-get install -y libcurl4-openssl-dev build-essential

git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$HOME/.rbenv/shims:$PATH"' >> ~/.bash_profile

eval "$(rbenv init -)" >> ~/.bash_profile

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

rbenv install 2.3.1

gem install bundler
SCRIPT

VAGRANTFILE_API_VERSION = "2"
ENV['VAGRANT_DEFAULT_PROVIDER'] ||= 'docker'
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.network "forwarded_port", guest: 3000, host: 3000

  config.vm.define "railsgoat" do |rg|
    rg.vm.box = 'ubuntu/trusty64'

    # rg.vm.provider "docker" do |d|
    #   d.image = "mccabe615/railsgoat"
    #   d.name = "railsgoat"
    #   d.ports = ["3000:3000"]
    #   d.vagrant_vagrantfile = "./Vagrantfile.proxy"
    # end
  end

end

# RAILS_ENV=mysql bundle exec rails server -b 0.0.0.0
