# KDiscordCommand
This library is designed to make working with discord librarys like discord4j a breeze specifically designed to work with kotlin(although in theory should work with any other jvm language too, although Kotlin is by far the prefered and most tested/supported method)

## Core version
[ ![Download](https://api.bintray.com/packages/johnfg10/KDiscordCommandFramework/KDiscordCommandCore/images/download.svg) ](https://bintray.com/johnfg10/KDiscordCommandFramework/KDiscordCommandCore/_latestVersion)
```gradle
repositories {
    jcenter()
    maven {
        url "https://dl.bintray.com/johnfg10/KDiscordCommandFramework"
    }
}

compile 'io.github.johnfg10:KDiscordCommandCore:*LATEST_VERSION*'
```

## Discord 4j version
[ ![Download](https://api.bintray.com/packages/johnfg10/KDiscordCommandFramework/KDiscordCommandDiscord4j/images/download.svg) ](https://bintray.com/johnfg10/KDiscordCommandFramework/KDiscordCommandDiscord4j/_latestVersion)
```gradle
repositories {
    jcenter()
    maven {
        url  "https://jitpack.io"
    }
    maven {
        url "https://dl.bintray.com/johnfg10/KDiscordCommandFramework"
    }
}

compile 'io.github.johnfg10:KDiscordCommandDiscord4j:*LATEST_VERSION*'
```

example code registration:
```kotlin
    //requires a refrence to discord4js IDiscordClient in this example this is repusented by client
    val kDiscord = KDiscord4J(client, "-")
    //you may either use the operator overload to add a class
    kDiscord+test::class
    //or use the regstration method
    kDiscord.RegisterCommand(test::class)
```

example code command: 
```kotlin
    @Command("hello", ["hello", "hi"], "")
    fun hello(@CommandArg(CommandArgumentType.Channel) channel: IChannel, @CommandArg(CommandArgumentType.User)user: IUser){
        channel.sendMessage("Hello, ${user.name}")
    }
```

## Testbot
test bot takes one command line argument, a discord token which it uses to login to it is simply a area in which i can test new features and ensure old ones still work if you want to know about features thats most likely a good place to start!
