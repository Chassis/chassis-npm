# npm extension for Chassis
The npm extension automatically sets up your Chassis instance to be able to use that latest npm release inside your Chassis box.

## Activation
Ensure you have a Chassis instance set up locally then clone this extension.

```
# In your Chassis dir:
git clone --recursive https://github.com/Chassis/npm.git extensions/npm
```

Then you'll need to reprovision
```
cd ..
vagrant provision
```

Alternatively you can add the extension to one of your yaml config files. e.g.
```
# Extensions
#
# Install a list of extensions automatically
extensions:
    - chassis/npm
```

Then you'll need to reprovision

```
cd ..
vagrant provision
```

npm has now been installed inside your Chassis box.

## Installing Npm dependencies

You can have Chassis automatically run `npm install` in a number of directories in your project by adding a list of directories in one of your [yaml](http://docs.chassis.io/en/latest/config/) files. e.g.
```
npm:
    paths:
        # Use absolute paths on the VM. For a default Chassis installation this should be:
        - /vagrant/content/plugins/yourplugin
        - /vagrant/content/themes/atheme
        # If you're using paths (http://docs.chassis.io/en/latest/config/#paths) in Chassis this should be:
        - /chassis/content/plugins/yourplugin
        - /chassis/content/themes/atheme
```

You'll need to run `vagrant provision` for those to be installed if you'd added them after your first initial Chassis `vagrant up`.

