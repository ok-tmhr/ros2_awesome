# ROS 2 awesome

## Schema Support for ROS 2 Launch Files

`ros2_awesome` provides **schema definitions** for ROS 2 launch files in both **YAML** and **XML** formats.
These schemas enable:

- Validation
- Auto-completion
- Hover documentation
- Error checking

in editors such as **VS Code**.

## 📌 Available Schemas

### YAML Schema

```md
https://ok-tmhr.github.io/ros2_awesome/schema/launch.yaml
```

### XML Schema

```md
https://ok-tmhr.github.io/ros2_awesome/schema/launch_ros.xsd
```

## 1. Using the Schema in YAML Launch Files

You can explicitly specify the schema at the top of your `.launch.yaml` file:

```yaml
# yaml-language-server: $schema=https://ok-tmhr.github.io/ros2_awesome/schema/launch.yaml

launch:
  - arg:
      name: example
```

This method is **portable** and works in any environment.
See the `sample/` directory for complete examples.

## 2. Using the Schema in XML Launch Files

Add the schema reference inside the `<launch>` tag:

```xml
<launch
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:noNamespaceSchemaLocation="https://ok-tmhr.github.io/ros2_awesome/schema/launch_ros.xsd">

  <arg name="example"/>
</launch>
```

## 3. VS Code: Associate the Schema Automatically

If you prefer not to write `$schema` in every YAML file,
VS Code can automatically apply the schema based on file patterns.

Open **Settings (JSON)** and add:

```json
{
  "yaml.schemas": {
    "https://ok-tmhr.github.io/ros2_awesome/schema/launch.yaml": [
      "*.launch.yaml",
      "*.launch.yml"
    ]
  }
}
```

Now all launch YAML files will automatically use the schema.

## 4. VS Code Snippets for Launch Substitutions

This repository includes a snippet extension:

```md
launch_substitution.json
```

It provides auto-completion for ROS 2 substitution syntax:

```md
$(var name)
$(env FOO)
$(not value)
$(eval ...)
```

### Substitution in Parameter Files

ROS 2 substitutions are not limited to launch files.
They also work inside parameter YAML files when loaded through a launch file.

### Install as a local VS Code extension

1. Clone this repository
2. Open command pallet (`ctrl + shift + p`)
3. Run **Developer: Install Extension from Location...**
4. Choose repository's directory

VS Code treats snippet JSON files as installable local extensions.

### Features

- Typing `$` triggers substitution snippets
- Typing `not` triggers `$(not …)`
- Works in both YAML and XML launch files
- Fully customizable

## 5. Sample Files

The `sample/` directory contains:

- YAML launch examples using `$schema`
- XML launch examples using XSD

These samples are the quickest way to understand how the schema behaves.

## 6. Project Goals

- Provide a **strict, complete, and editor-friendly** schema for ROS 2 launch files
- Improve developer experience with **auto-completion** and **error detection**
- Offer **snippets** for common substitution patterns
- Maintain compatibility with VS Code and other YAML/XML tooling

## 7. Contributions

Issues and PRs are welcome.
Schema improvements, missing elements, or substitution patterns can be added incrementally.
