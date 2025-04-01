# agile-final-project


@startuml

class Salle {
  +id: Integer
  +type: String // "cours" ou "TP"
}

class SeanceEnseignement {
  +id: Integer
  +type: String // "cours magistral", "travail dirigé", "travail pratique"
}

class Planning {
  +id: Integer
  +date: Date
  +jour: String
  +heureDebut: Time
  +heureFin: Time
}

class SalleSeance {
  +salleId: Integer
  +seanceId: Integer
  +planningId: Integer
}

Salle "1" -- "*" SalleSeance : accueille >
SeanceEnseignement "1" -- "*" SalleSeance : se déroule dans >
Planning "1" -- "*" SalleSeance : est planifié pour >

@enduml
