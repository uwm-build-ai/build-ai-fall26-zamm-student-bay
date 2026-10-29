# 🐾 Adoption Day

```
### 🌦 Walk
**Three campuses, one sky.** Pick a campus: the dogs go out when it is dry.

[Walk](#)
{: .runner src="../module_06/walk.md" bench="true" }

### 🙋 Author
## 💼 Hire me!

[My CV](#)
{: .runner src="../module_01/cv.md" bench="true" }
```
{: .tabs #menu }

Play the tour
{: .avatar_trigger target="app_tour" }

```yaml
face:
  skin: "#e0ac69"
  hair: full
  hair_color: "#4a3426"
  glasses: none
  wear: shirt
script:
  - do: read
    say: "Welcome to Adoption Day. Three campuses, and the sky over each one."
  - at: campus_grid
    do: select
    with: Racine
    say: "Pick Racine: the map flies south, and the sky is asked again, for Racine."
  - at: campus_grid
    do: select
    with: Milwaukee
    say: "And back to Milwaukee. Dry and not too hot: the dogs go out."
  - at: menu
    do: open
    with: Author
    say: "I'm Michel. I built this in one semester, and Brewers rock!"
  - do: read
stories: {}
```
{: .avatar #app_tour size="100" }

[Recording](https://youtu.be/TFo_RHdMvFk)
{: .video }
