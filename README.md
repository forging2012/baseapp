BaseApp
=======

#### A starter application built in [Go](http://golang.org) on top of the [Revel Web Framework](https://revel.github.io) ####

BaseApp is a Revel web application that provides a starter application with the following features:

* Basic pages (Home, About Us, Contact Us, etc)
* Account registration (including safe storage of passwords with [bcrypt](https://en.wikipedia.org/wiki/Bcrypt))
* Account log in
* Account recovery (via configurable e-mail settings)
* Public user profiles (with integration with Gravatar for profile photos and edit functionality)
* Public user posts (with full Markdown support and edit + delete functionality)
* Full form validation
* Full non-interactive and interactive testing framework (Test-driven development process)

### Quick Start ####

#### Prerequisites ####

You will need a [functioning Revel installation](https://revel.github.io/tutorial/gettingstarted.html) for BaseApp to work.

#### Installing BaseApp ####

To get [https;//github.com/richtr/baseapp](BaseApp), run

    go get github.com/richtr/baseapp

This command does a couple things:

* Go uses git to clone the repository into $GOPATH/src/github.com/richtr/baseapp/
* Go transitively finds all of the dependencies and runs go get on them as well.

#### Running BaseApp ####

Before you can start using BaseApp you will need to add your own `app.conf` file in your `conf/` directory. You can copy and use the <a href="https;//github.com/richtr/baseapp/blob/master/conf/app.conf.default">default configuration file</a> with

    cp ./github.com/richtr/baseapp/conf/app.conf.default ./github.com/richtr/baseapp/conf/app.conf

Note: It is highly recommended that you review the configuration options available in `app.conf.default` before you run your project for the first time!

Once you have setup an `app.conf` file you can start BaseApp _in test mode_, with

    revel run github.com/richtr/baseapp test

Point your browser to your BaseApp installation at `http://localhost:9000` (or the path you specified in your `app.conf` file) and away you go.

### BaseApp Run Modes ###

BaseApp can be run in three different modes that are each useful for different stages of application development:

1. `test` mode: Uses an *in-memory* sqlite3 datastore that is created and populated with basic data which is always wiped when your application ends.

    You can run BaseApp in `test` mode as follows:

        $> revel run baseapp/ test

    Or to run the non-interactive command-line test suite use:

        $> revel test baseapp/ test

2. `dev` mode [default mode]: Uses a blank sqlite3/mysql/postgres datastore that is created if it does not already exist at your chosen location and persists whenever your application is restarted. Outputs detailed error messages if something goes wrong in your application.

    You can run BaseApp in `dev` mode as follows:

        $> revel run baseapp/ dev

    Or, simply:

        $> revel run baseapp/

3. `prod` mode: Uses a blank sqlite3/mysql/postgres datastore that is created if it does not already exist at your chosen location and persists whenever your application is restarted. Outputs user-friendly error messages if something goes wrong in your application.

    You can run BaseApp in `prod` mode as follows:

        $> revel run baseapp/ prod

Note: Both `dev` and `prod` modes require a configured backend DB. See [app.conf.default](https;//github.com/richtr/baseapp/blob/master/conf/app.conf.default). The `test` mode creates an in-memory database representation that dies when the app dies)

### Feedback ###

If you find any bugs or issues please report them on the [BaseApp Issue Tracker](https://github.com/richtr/baseapp/issues).

If you would like to contribute to this project please consider [forking this repo](https://github.com/richtr/baseapp/fork_select), making your changes and then creating a new [Pull Request](https://github.com/richtr/baseapp/pulls) back to the main code repository.

### License ###

MIT. Copyright (c) Rich Tibbett.

See the [LICENSE](https://github.com/richtr/baseapp/blob/master/LICENSE) file.