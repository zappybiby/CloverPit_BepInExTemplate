Basic info about the project
1. This project is a forked version of a Example Bepinex Mod Template that allows developers to create their own nuget package so that it can be installed and used as a dotnet template when creating new mods for the game.
2. The idea is that other mod developers can install this nuget package that we create from the project and use the base template it creates to start making a plugin for the game "CloverPit"
3. This will be a Bepinex Template nuget package that users will be able to install and then use to make a bepinex mod template for the game CloverPit. 

When modifying this template, keep in mind the following:
1. This template is designed for use with Windows OS only (Including WSL environments)
2. CloverPit is a Unity 6 Game and therefore our dotnet target framework is netstandard2.1 

This template uses Hamunii.BepInEx.AutoPlugin 
Basics of AutoPlugin:
```
BepInEx.AutoPlugin is an incremental C# source generator that takes the following properties from your project:

<PropertyGroup>
  <AssemblyName>com.example.ExamplePlugin</AssemblyName>
  <AssemblyTitle>ExamplePlugin</AssemblyTitle>
  <Version>0.1.0</Version>
</PropertyGroup>
And generates a partial class for your partial plugin class decorated with the BepInAutoPluginAttribute, decorating the generated class with the BepInPluginAttribute using the above properties:

[BepInEx.BepInPlugin(ExamplePlugin.Id, "ExamplePlugin", "0.1.0")]
partial class ExamplePlugin : BaseUnityPlugin
{
    public const string Id = "com.example.ExamplePlugin";
    public static string Name => "ExamplePlugin";
    public static string Version => "0.1.0";
}
```