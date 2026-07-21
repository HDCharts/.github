<p align="center">
  <img
    src="https://github.com/dautovicharis/Charts/assets/7049715/4150f102-1b05-4fd7-ab01-63480d2e6d50"
    alt="HDCharts"
    width="260"
  />
</p>

<p align="center">
  <a href="https://central.sonatype.com/artifact/io.github.dautovicharis/charts/overview">
    <img src="https://img.shields.io/maven-central/v/io.github.dautovicharis/charts.svg?label=Maven%20Central" alt="Maven Central" />
  </a>
  <a href="https://central.sonatype.com/repository/maven-snapshots/io/github/dautovicharis/charts/maven-metadata.xml">
    <img src="https://img.shields.io/maven-metadata/v?metadataUrl=https%3A%2F%2Fcentral.sonatype.com%2Frepository%2Fmaven-snapshots%2Fio%2Fgithub%2Fdautovicharis%2Fcharts%2Fmaven-metadata.xml&label=Snapshots&color=4285F4" alt="Snapshots" />
  </a>
</p>

<p align="center">
  A Kotlin Multiplatform chart library built with Jetpack Compose.
</p>

<p align="center">
  <a href="https://charts.harisdautovic.com/">Documentation</a>
  ·
  <a href="https://charts.harisdautovic.com/demo">Demo</a>
  ·
  <a href="https://charts.harisdautovic.com/playground">Playground</a>
  ·
  <a href="https://central.sonatype.com/artifact/io.github.dautovicharis/charts/overview">Maven Central</a>
</p>

<p align="center">
  <a href="https://charts.harisdautovic.com/demo">
    <img width="893" alt="HDCharts demo" src="https://github.com/user-attachments/assets/9bd7fc79-93c2-434a-a70c-d3a3a6dc9db4" />
  </a>
</p>

## Projects

| Project | Description |
| --- | --- |
| [charts](https://github.com/HDCharts/charts) | Core Kotlin Multiplatform chart library for Compose apps. |
| [charts-docs](https://github.com/HDCharts/charts-docs) | Documentation site and published examples. |
| [charts-playground](https://github.com/HDCharts/charts-playground) | Interactive playground for trying chart configurations. |
| [compose-gif-recorder](https://github.com/hdcodedev/compose-gif-recorder) | Utility used to record Compose chart examples as GIFs. |

## Get Started

Install the library from Maven Central:

```kotlin
commonMain.dependencies {
    implementation("io.github.dautovicharis:charts:<version>")
}
```

Use individual modules when you only need specific chart types:

```kotlin
commonMain.dependencies {
    implementation("io.github.dautovicharis:charts-line:<version>")
    implementation("io.github.dautovicharis:charts-pie:<version>")
    implementation("io.github.dautovicharis:charts-bar:<version>")
    implementation("io.github.dautovicharis:charts-histogram:<version>")
    implementation("io.github.dautovicharis:charts-stacked-bar:<version>")
    implementation("io.github.dautovicharis:charts-stacked-area:<version>")
    implementation("io.github.dautovicharis:charts-radar:<version>")
}
```

## Example

```kotlin
@Composable
fun BasicLineChart() {
    val values = listOf(42f, 38f, 45f, 51f, 47f, 54f, 49f)
    val labels = listOf("Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun")

    val dataSet = values.toChartDataSet(
        title = "Daily Support Tickets",
        labels = labels,
    )

    LineChart(dataSet)
}
```

## Contributing

Start with the [documentation](https://charts.harisdautovic.com/) and use [charts-projects](https://github.com/HDCharts/charts-projects) to set up the local workspace. See the [contributing guide](https://github.com/HDCharts/.github/blob/main/CONTRIBUTING.md) for pull request guidelines.
