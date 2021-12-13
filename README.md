# CLC3-GitFlow
CLC3 GitFlow Projekt

## Sequence diagrams for all use cases

```puml
  title Usecase 1

  GitLab->GitLab: Feature Branch in Develop Branch
  GitLab->SonarQube: Codequalität überprüfen
  SonarQube->GitLab: Codequalität Resultat
  GitLab->GitLab: Merge blockieren falls Codequalität nicht passt. Andernfalls Merge zulassen.
  GitLab->User: Info wenn Codequalität failed.
```

```puml
  title Usecase 2

  GitLab->GitLab: Neue Version auf Release Branch
  GitLab->GitLab: Neuer Tag wird erstellt.
  GitLab->DockerHub: Image wird im Dockerhub hinterlegt.

```

```puml
  title Usecase 3

  GitLab->GitLab: Hotfix wird erkannt als Branch
  GitLab->GitLab: Nach Hofix merge wird automatisch neuer Tag erstellt.
  GitLab->DockerHub: Hofix wird mit einer (major, Minor, Patch) Version released.
  GitLab->User: Info über HotfixAlice

```

```puml
  title Usecase 4

  GitLab->GitLab: Änderungen im Major und Minor Level wird erkannt.
  GitLab->GitLab: Readme Datei wird automatisch mit Info angepasst.

```

```puml
  title Usecase 5

  GitLab<-->ExternalUrl: Datensätze werden regelmäßig abgefragt und im Repo gespeichert.
  GitLab->GitLab: Nach Update der Datensätze werden die Daten automatisch mir R gecleaned.
  GitLab->GitLab: Datensätze werden versioniert.
```
