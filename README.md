# ROS 2 Launch Substitutions Snippets

A lightweight VSCode snippet extension for ROS 2 launch substitution expressions.

:contentReference[oaicite:0]{index=0}

This extension provides reusable snippet templates for ROS 2 launch substitutions, compatible with:

- YAML launch files
- XML launch files
- ROS 2 parameter files

## 🚀 Features

All snippets follow ROS 2 launch substitution syntax:

```text
$(substitution args...)
```

## 📁 Supported Formats

### YAML launch files

Works with standard ROS 2 YAML launch descriptions.

### XML launch files

Compatible with ROS 2 XML launch definitions.

### ROS 2 parameter files

These snippets can also be used in ROS 2 parameter YAML files.

⚠️ Note:
When using substitutions inside parameter files, enable substitution support on a launch file:

```yaml
allow_substs: true
```

This is required for substitution expressions to be evaluated at runtime.

## 📌 Design Notes

- Snippets are intentionally shared across YAML and XML for consistency
- No runtime logic is included — only text expansion templates
- Focus is on ROS 2 launch substitution readability and speed of authoring

## 🧠 ROS 2 Compatibility

This extension targets standard ROS 2 launch substitution behavior as defined in the launch system.

It is compatible with:

- ROS 2 launch files
- Launch XML
- Launch YAML descriptions
- Parameter YAML files (with `allow_substs: true`)

## 📄 License

Apache 2.0
