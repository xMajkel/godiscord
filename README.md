# godiscord

A package for the creation and deliver of embeds for [Discord](https://discord.com)

## Usage:
```golang
package main

import "github.com/xMajkel/godiscord"

func main() {
    //Create a new embed object
    embed := godiscord.NewEmbed("Title", "Description", "URL")

    //Overrides webhook's username and/or avatar URL
    embed.SetUser("Username", "AvatarURL")

    //Sets the content (above the embed), for @ mentions
    embed.SetContent("@everyone")

    //Creates a new field and adds it to the embed
    //boolean represents whether the field is inline or not
    embed.AddField("This is a field", "This is the value", true)

    //Sets the thumbail of the embed
    embed.SetThumbnail("URL")

    //Sets image of embed
    embed.SetImage("URL")

    //Sets color of embed given hexcode
    embed.SetColor("#F1B379")

    //Sets author of embed given name, icon url, and URL
    //Can pass in empty string for IconURL or URL
    embed.SetAuthor("Name", "URL", "IconURL") 
    //also valid
    embed.SetAuthor("Name", "URL", "") 

    //Sets footer of embed given name and IconURL
    //Can pass in empty string for IconURL
    embed.SetFooter("Text", "IconURL")
    //also valid
    embed.SetFooter("Text", "")

    //Sets timestamp in the footer
    embed.SetTimestamp()

    //Send embed to given webhook
    embed.SendToWebhook("Webhook URL")
}
```
