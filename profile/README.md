<p align="center">
  <img
    src="https://raw.githubusercontent.com/HDCharts/charts/main/readme-assets/hdcharts-logo-light.svg#gh-light-mode-only"
    alt="HDCharts logo"
    align="center"
    width="300"
  />
  <img
    src="https://raw.githubusercontent.com/HDCharts/charts/main/readme-assets/hdcharts-logo-dark.svg#gh-dark-mode-only"
    alt="HDCharts logo"
    align="center"
    width="300"
  />
</p>

<p align="center">
  <a href="https://central.sonatype.com/artifact/io.github.hdcharts/charts/overview">
    <img src="https://img.shields.io/maven-central/v/io.github.hdcharts/charts.svg?label=Maven%20Central" alt="Maven Central" />
  </a>
  <a href="https://central.sonatype.com/repository/maven-snapshots/io/github/hdcharts/charts/maven-metadata.xml">
    <img src="https://img.shields.io/maven-metadata/v?metadataUrl=https%3A%2F%2Fcentral.sonatype.com%2Frepository%2Fmaven-snapshots%2Fio%2Fgithub%2Fhdcharts%2Fcharts%2Fmaven-metadata.xml&strategy=latestProperty&label=Snapshots&color=4285F4" alt="Snapshots" />
  </a>
  <img src="https://img.shields.io/badge/Compose_Multiplatform-1.12.2-4285F4?logo=jetpackcompose" alt="Compose Multiplatform 1.12.2" />
  <img src="https://img.shields.io/badge/Kotlin_Multiplatform-2.4.21-0095D5?logo=kotlin" alt="Kotlin Multiplatform 2.4.21" />
  <img src="https://img.shields.io/badge/AGP-9.5.0-2E7D32?logo=android" alt="Android Gradle Plugin 9.5.0" />
</p>

<p align="center">
  A Kotlin Multiplatform chart library built with Jetpack Compose.
</p>

<p align="center">
  <a href="https://charts.hdcode.dev/">Documentation</a>
  ·
  <a href="https://charts.hdcode.dev/demo">Production Demo</a>
  ·
  <a href="https://charts.hdcode.dev/demo/snapshot/">Snapshot Demo</a>
  ·
  <a href="https://central.sonatype.com/artifact/io.github.hdcharts/charts/overview">Maven Central</a>
</p>

<p align="center">
  <picture>
    <source
      media="(prefers-color-scheme: dark)"
      srcset="https://raw.githubusercontent.com/HDCharts/charts/main/sample/androidApp/src/screenshotTestDebug/reference/io/github/hdcharts/app/screenshot/ReadmeScreenshotTestKt/ReadmeShowcasePreview_README%20dark_278d6fe8_0.png"
    />
    <img
      width="893"
      alt="HDCharts histogram, stacked area, bar, donut, multi-line, and radar charts"
      src="https://raw.githubusercontent.com/HDCharts/charts/main/sample/androidApp/src/screenshotTestDebug/reference/io/github/hdcharts/app/screenshot/ReadmeScreenshotTestKt/ReadmeShowcasePreview_README%20light_9696eabb_0.png"
    />
  </picture>
</p>

## Projects

| Project | Description |
| --- | --- |
| [charts](https://github.com/HDCharts/charts) | Core Kotlin Multiplatform chart library for Compose apps. |
| [charts-docs](https://github.com/HDCharts/charts-docs) | Documentation site and published examples. |
| [compose-gif-recorder](https://github.com/hdcodedev/compose-gif-recorder) | Utility used to record Compose chart examples as GIFs. |

## Get Started

### All chart types

Use the umbrella artifact when you want all chart types with the simplest setup.

```kotlin
commonMain.dependencies {
    implementation("io.github.hdcharts:charts:<version>")
}
```

### Individual chart modules

Use independent modules when you want only specific chart types and smaller dependency footprint.

```kotlin
commonMain.dependencies {
    implementation("io.github.hdcharts:line:<version>")
    implementation("io.github.hdcharts:pie:<version>")
    implementation("io.github.hdcharts:bar:<version>")
    implementation("io.github.hdcharts:histogram:<version>")
    implementation("io.github.hdcharts:stacked-bar:<version>")
    implementation("io.github.hdcharts:stacked-area:<version>")
    implementation("io.github.hdcharts:radar:<version>")
    implementation("io.github.hdcharts:gauge:<version>")
    implementation("io.github.hdcharts:scatter:<version>")
    implementation("io.github.hdcharts:heatmap:<version>")
    implementation("io.github.hdcharts:waterfall:<version>")
}
```

### BOM

Use BOM for version alignment where Gradle platforms are supported.
For KMP `commonMain`, keep explicit versions as shown above.

```kotlin
dependencies {
    implementation(platform("io.github.hdcharts:bom:<version>"))
    implementation("io.github.hdcharts:line")
    implementation("io.github.hdcharts:pie")
    implementation("io.github.hdcharts:bar")
    implementation("io.github.hdcharts:histogram")
    implementation("io.github.hdcharts:stacked-bar")
    implementation("io.github.hdcharts:stacked-area")
    implementation("io.github.hdcharts:radar")
    implementation("io.github.hdcharts:gauge")
    implementation("io.github.hdcharts:scatter")
    implementation("io.github.hdcharts:heatmap")
    implementation("io.github.hdcharts:waterfall")
}
```

## Example

```kotlin
import androidx.compose.runtime.Composable
import io.github.hdcharts.core.model.toChartData
import io.github.hdcharts.line.LineChart

data class Nutrient(val name: String, val calories: Double)

@Composable
fun NutrientCaloriesChart() {
    val nutrients = listOf(
        Nutrient("Carbs", 240.0),
        Nutrient("Protein", 180.0),
        Nutrient("Fat", 320.0),
    )

    val data = nutrients.toChartData(
        value = { it.calories },
        category = { it.name },
    )

    LineChart(
        data = data,
        title = "Calories by nutrient",
    )
}
```

## Contributing

Start with [charts-workspace](https://github.com/HDCharts/charts-workspace) to set up the local workspace.
