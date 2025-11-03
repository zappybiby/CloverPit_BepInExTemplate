# BepInExModTemplate

Describe your project here!

## Template Instructions

You can remove this section after you've set up your project.

Next steps:

- Create a copy of the `Config.Build.user.props.template` file and name it `Config.Build.user.props`
  - This will automate copying your plugin assembly to `BepInEx/plugins/`
  - Configure the paths to point to your game path and your `BepInEx/plugins/`
  - Game assembly references should work if the path to the game is valid
- Search `TODO` in the whole project to see what you should configure or modify

### Thunderstore Packaging

This template comes with Thunderstore packaging built-in, using [TCLI](<https://github.com/thunderstore-io/thunderstore-cli>).

You can build Thunderstore packages by building with release configuration:

```sh
dotnet build -c Release -v d
```

> [!NOTE]  
> You can learn about different build options with `dotnet build --help`.  
> `-c` is short for `--configuration` and `-v d` is `--verbosity detailed`.

The built package will be found at `artifacts/thunderstore/`.

### Referencing Thunderstore Mods

- Add the dependency to your project file so your plugin can use it:

  ```xml
  <ItemGroup>
    <PackageReference Include="Team-ModName" Version="1.2.3" Private="False" />
  </ItemGroup>
  ```

  The Thunderstore NuGet feed is already set up. Keeping `Private="False"` stops the dependency’s files from being copied into your build output; your players should get them from Thunderstore.

- Add the same entry to `thunderstore.toml` so Thunderstore and mod managers install it automatically:

  ```toml
  [package.dependencies]
  Team-ModName = "1.2.3"
  ```

- Match the version number in both files. The project file supports your development environment, while `thunderstore.toml` describes what your published package needs.
