# Enable Comments

## Explanation

As of version 2.6, Pickles includes Gherkin #-style comments. As of version 2.7, this inclusion is configurable.

## Default Value

true

## Usage

### Console

```
Pickles.exe --enableComments=true
```

```
Pickles.exe -cmd=true
```

### Powershell

```
Pickle-Features -EnableComments true
```

### MSBuild

```xml
<target Name="document">
    <pickles EnableComments="true" />
</target>
```
