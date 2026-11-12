# 🧭 Study Buddy

````
### 🎯 Problem

[My choice](welcome.md)
{: .import bench="true" }

**{= my_project.first.name }** — {= my_project.first.story.replace(my_project.first.character, persona.name or my_project.first.character) }

```yaml
role: ""
```
{: .persona #persona save="zim.yaml" }

```yaml
product: ""
```
{: .pitch #pitch save="pitch.yaml" persona="persona" }

### 🗺️ Map and backlog

[My map](#)
{: .runner src="map.md" bench="true" title="" }

```yaml
- { as_a: "", headline: "", i_want: "", so_that: "", value_why: "", tech_note: "" }
```
{: .dataset #backlog }

```csv
my features, read from my space
```
{: .datagrid source="backlog" save="features.yaml" columns="headline, i_want, business_value, value_why, tech_note" height="260" title="📋 My features" }

### 🙋 Author

[My CV](#)
{: .runner src="../module_01/cv.md" bench="true" }
````
{: .tabs #menu }