# Добавляем SourceLink

## Зачем
[SourceLink](https://github.com/ctaggart/SourceLink)

SourceLink позволяет скачивать исходники во время отладки прямо с hithub или с других серверов контроля версий. Это более простая альтернатива Source серверам, которые хранят pdb файлы.

Больше не надо думать поставлять ли pdb в nuget пакете. Не нужно пушить pdb на Source сервера.

## Шаги

### Подключение
Самый простой способ подключить SourceLink сразу к нескольким проектам это использовать файл `Directory.Build.props`:

```xml
<Project>
  <ItemGroup>
    <PackageReference Include="SourceLink.Create.CommandLine" Version="2.8.0" PrivateAssets="All" /> 
  </ItemGroup>
</Project>
```

Без всякой дополнительной конфигурации `SourceLink.Create.CommandLine` будет работать с репозиториями из GitHub и BitBucket.

Можно контролировать запуск SourceLink с помощью MsBuild параметра `/p:SourceLinkCreate=true`

### Portable PDB format
Для работы SourceLink также требуется компилировать pdb в [Portable PDB format](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md).
Portable PDB format является кросс платформенным, а также имеет гораздо меньший объем чем Windows PDB files.

Кроме того имеется опция встраивания pdb прямо в dll или exe (embedded), что очень удобно для доставки пакетов. Я предпочитаю также поставлять эти настройки в `Directory.Build.props`:

```xml
<Project>
  <ItemGroup>
    <PackageReference Include="SourceLink.Create.CommandLine" Version="2.8.0" PrivateAssets="All" /> 
  </ItemGroup>
  <PropertyGroup>
    <DebugType>embedded</DebugType>
    <GenerateDocumentationFile>true</GenerateDocumentationFile>
  </PropertyGroup>
</Project>
```

## В результате
- Pdb файлы генерируются в Portable PDB format и внедряются прямо в сборку
- SourceLink подключен к проектам
- Запуск SourceLink регулируется параметром `SourceLinkCreate`
- SourceLink на этапе компиляции переписывает в pdb файлах локальные пути на пути в GitHub