# 🐕 Adoption Day — Dogs

```csv
name,breed,age,fee,campus,pic
Lucky,Beagle,3,150,Milwaukee,101
Wanda,Poodle,5,120,Milwaukee,102
Hazel,Lab mix,2,150,Milwaukee,103
Peanut,Chihuahua,7,95,Milwaukee,104
Bo,Terrier,4,120,Ozaukee,105
Mila,Shepherd mix,1,180,Ozaukee,106
Rex,Boxer,6,95,Racine,107
Daisy,Corgi mix,2,180,Racine,108
Gus,Great Pyrenees,5,120,Racine,109
Scout,Husky mix,2,180,Milwauke,110
Biscuit,Beagle,4,150,MKE,111
Nova,Lab,1,180,Downtown,112
```
{: .dataset #dogs }

```csv
bound to the dogs dataset above — edits write straight back to it
```
{: .datagrid source="dogs" #all_dogs editable="true" save="dogs.yaml" compute="photo = 'https://placedog.net/400/240?id=' + str(pic)" height="360" title="🐕 All our dogs — double-click to repair" }

```yaml
```
{: .form master="all_dogs" #dog_form }
