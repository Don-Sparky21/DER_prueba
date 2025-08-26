# DER_prueba
erDiagram
	Pago }o--|| concepto : references
	PagoPaciente }o--|| Pago : references
	PagoPaciente }o--|| Turno : references
	TurnoPaciente }o--|| Turno : references
	MedicoEspecialidad }o--|| Especialidad : references
	HistoriaPaciente }o--|| Historia : references
	TurnoPaciente }o--|| Medico : references
	MedicoEspecialidad }o--|| Medico : references
	HistoriaPaciente }o--|| Medico : references
	Turno }o--|| TurnoEstado : references
	Paciente }o--|| Pais : references
	HistoriaPaciente }o--|| Paciente : references
	TurnoPaciente }o--|| Paciente : references
	PagoPaciente }o--|| Paciente : references

	CLIENTES {
		NVARCHAR(50) Número_de_cliente
		NVARCHAR(100) Nombre_de_cliente
		NVARCHAR(50) STATUS
	}

	concepto {
		TINYINT idConcepto
		VARCHAR(100) descripcion
	}

	Especialidad {
		ESPECIALIDAD idEspecialidad
		VARCHAR(30) Especialidad
		VARCHAR(50) descripcion
	}

	Especialidad2 {
		ESPECIALIDAD idEspecialidad
		VARCHAR(30) Especialidad
		VARCHAR(50) descripcion
	}

	Especialidad3 {
		ESPECIALIDAD idEspecialidad
		VARCHAR(30) Especialidad
		VARCHAR(50) descripcion
	}

	Historia {
		HISTORIA idHistoria
		DATETIME fechaHistoria
		OBSERVACION observacion
	}

	HistoriaPaciente {
		HISTORIA idHistoria
		PACIENTE idPaciente
		MEDICO idMedico
	}

	Medico {
		MEDICO idMedico
		VARCHAR(50) nombre
		VARCHAR(50) apellido
	}

	MedicoEspecialidad {
		MEDICO idMedico
		ESPECIALIDAD idEspecialidad
		VARCHAR(50) descripcion
	}

	Paciente {
		PACIENTE idPaciente
		VARCHAR(20) dni
		VARCHAR(50) nombre
		VARCHAR(50) apellido
		DATE fNacimiento
		VARCHAR(50) domicilio
		CHAR(3) idPais
		VARCHAR(20) telefono
		VARCHAR(30) email
		OBSERVACION observacion
	}

	Paciente1 {
		INT idPaciente
		VARCHAR(50) nombre
		VARCHAR(50) apellido
		DATE fNacimiento
		VARCHAR(50) domicilio
		CHAR(3) idPais
		VARCHAR(20) telefono
		VARCHAR(30) email
		VARCHAR(1000) observacion
		DATETIME fechaAlta
	}

	PacienteLog {
		PACIENTE idpaciente
		CHAR(3) idpais
		DATETIME fechaAlta
		DATETIME fechaModificacion
		DATETIME fechaBaja
	}

	Pago {
		INT idPago
		TINYINT concepto
		DATETIME fecha
		MONEY monto
		TINYINT estado
		OBSERVACION observacion
	}

	PagoPaciente {
		INT idPago
		PACIENTE idPaciente
		INT idTurno
	}

	Pais {
		CHAR(3) idPais
		VARCHAR(30) Pais
	}

	sysdiagrams {
		SYSNAME name
		INT principal_id
		INT diagram_id
		INT version
		VARBINARY(MAX) definition
	}

	Turno {
		TURNO idTurno
		DATETIME fechaTurno
		SMALLINT estado
		OBSERVACION observacion
	}

	TurnoEstado {
		SMALLINT idEstado
		VARCHAR(50) descripcion
	}

	TurnoPaciente {
		TURNO idTurno
		PACIENTE idPaciente
		MEDICO idMedico
	}
