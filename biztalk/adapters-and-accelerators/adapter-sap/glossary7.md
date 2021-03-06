---
title: Glosario para el adaptador de mySAP en BizTalk | Documentos de Microsoft
description: Términos y definiciones utilizadas por el adaptador de mySAP en el módulo de adaptador de BizTalk (BAP) comunes
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87db79be-e242-40fa-9897-8915e6fb5cae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976a8b885e02846e3927f55a6cf287a8f9414085
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218836"
---
# <a name="glossary"></a>Glosario
Los términos y definiciones siguientes se utilizan en [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].  
  
## <a name="a"></a>Un  
  
**adaptador**  
Un componente basado en WCF que facilita el intercambio de mensajes entre aplicaciones (por ejemplo, un sistema de línea de negocio) y BizTalk Server. El adaptador consiste en una serie de componentes de tiempo de diseño y de tiempo de ejecución para las operaciones de envío y recepción.

**cliente de adaptador**  
Una aplicación que interactúa con un sistema de línea de negocio (LOB) a través del adaptador.

**Aplicaciones empresariales avanzadas Programming (ABAP)**  
El lenguaje de programación de SAP.  
  
## <a name="b"></a>B  
  
**BAPI (Interfaces de programación de aplicaciones de negocio)**  
Interfaces estándares expuestas por el sistema SAP para intercambiar empresariales entre SAP y otros sistemas. BAPI se utiliza para integrar diferentes componentes, que están conectados entre sí a través de una red local o en Internet.

**enlace**  
Proceso por el que se vinculan los componentes y capas de software. Cuando se instala un componente de red, se establecen las relaciones de enlace y dependencias de los componentes. El enlace permite a los componentes comunicarse entre sí. En BizTalk Server, es una asignación establecida entre un extremo válido para los adaptadores de orquestaciones (puerto o vínculo de función) y los extremos físicos específicos de los adaptadores (puertos o entidades de envío y recepción).

**Servidor BizTalk Server**  
Se conecta a distintos programas de software. BizTalk Server permite crear y modificar la lógica de proceso que emplea dicho software. Además, BizTalk Server hace posible que los trabajadores de la información supervisen los procesos que están ejecutándose, interactúen con los socios comerciales y lleven a cabo otras tareas de tipo empresarial.

**objeto de negocios**  
Encapsula los datos SAP y los procesos en un modelo orientado a objetos. Los clientes externos invocan métodos llamados interfaces de objeto de aplicaciones empresariales (BAPI) para que actúe en el objeto (y sus artefactos SAP subyacentes). De forma predeterminada, el adaptador SAP no expone objetos comerciales para consumir las aplicaciones. Objetos de negocios solo están disponibles para las operaciones de cliente.

**Repositorio de objetos de negocios (BO)**  
Contiene todos los tipos de objeto de negocios SAP y los tipos de interfaz SAP, así como sus componentes (por ejemplo, los métodos y los atributos), residentes en el sistema SAP R/3.  
  
## <a name="c"></a>C  
  
**canal**  
Una implementación concreta de un elemento de enlace. El enlace representa la configuración y el canal es la implementación asociada a esa configuración. Por lo tanto, hay un canal asociado a cada elemento de enlace. Canales se apilan uno sobre otro para crear la implementación concreta del enlace: la pila de canales.

**página de códigos** básicamente una matriz de puntos de código. Todos los datos en la base de datos, incluidos los caracteres, se almacenan como secuencias de bytes. Para datos de caracteres, una página de códigos es la asignación entre una secuencia de bytes y un carácter.

**URI de conexión**  
Una cadena que identifica un recurso en un entorno distribuido. Los adaptadores utilizan una conexión Uniform Resource Identifier (URI) que contiene la información necesaria para establecer una conexión con el sistema LOB.

**contrato**  
Especifica la colección y estructura de mensajes necesarios para tener acceso a las operaciones que ofrece el servicio.
  
####  <a name="D"></a>D.  
  
**experiencia en tiempo de diseño**  
Los procedimientos y las operaciones que un programador lleva a cabo durante el tiempo de diseño; Por ejemplo, utilizando el complemento de consumir un proyecto de BizTalk de servicio de adaptador para recuperar esquemas de mensaje.  
  
## <a name="e"></a>E  
**dirección del extremo**  
Una dirección de red que identifica la ubicación de un punto de conexión de servicio de Windows Communication Foundation (WCF). Para un adaptador, la dirección del extremo se expresa como una conexión Uniform Resource Identifier (URI) que contiene parámetros de conexión y la ubicación. El adaptador puede utilizar para establecer una conexión con el sistema de línea de negocio (LOB) subyacente.

**Enterprise Single Sign-on system (SSO)**  
Base de datos de SSO, servidor secreto principal y uno o más de un servidor de inicio de sesión único empresarial (SSO). Estos servidores llevan a cabo la asignación entre las credenciales de Windows y las ajenas a éste, buscan las credenciales en la base de datos de SSO y se utilizan para administrar el sistema SSO. La base de datos de SSO también se utiliza como almacén de configuración para guardar los datos de las configuraciones personalizadas de los adaptadores.

**Lenguaje de marcado extensible (XML)**  
Lenguaje de marcado que se ha diseñado para describir los datos. Etiquetas XML no están predefinidas.  
  
## <a name="f"></a>F  
  
**módulos (función)**  
Procedimientos definidos en un sistema SAP como programas ABAP. Se trata de una parte de grupos de funciones que contienen una agrupación lógica de módulos de función. Módulos de función permiten a los clientes SAP reutilizar y encapsular funciones globales.
  
## <a name="g"></a>G  
  
**caché global de ensamblados (GAC)**  
Caché de código de todo el equipo que almacena los ensamblados instalados específicamente para que los compartan varias aplicaciones del equipo. Las aplicaciones implementadas en la caché global de ensamblados deben tener un nombre seguro.
  
## <a name="i"></a>I  
  
**operación entrante**  
Una operación que se invoca con un sistema de línea de negocio (LOB) en el adaptador.
  
**documentos intermedios (IDOC)**  
Un documento estructurado que se utiliza para intercambiar datos entre R/3, R/2 y los sistemas SAP no.  
  
## <a name="m"></a>M  
  
**metadatos**  
En WCF, hace referencia a una descripción del contrato expuesto por un servicio. Esto se conoce como la descripción del servicio y se expresa en un documento WSDL. Los metadatos expuestos por un adaptador describen (interfaz a) las operaciones que puede realizar en el sistema de línea de negocio (LOB) subyacente.

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
Las especificaciones para la creación de adaptadores de BizTalk mediante unos estándares abiertos basados en servicios Web.  
  
## <a name="o"></a>O  
  
**unidireccional**  
Un patrón de intercambio de mensajes (MEP) en el que el remitente envía un mensaje, pero no hay respuesta devuelto por el receptor. En BizTalk Server, MEP se conoce como patrones de comunicación.

**operación de salida**  
Una operación que se invoca el adaptador en el sistema de línea de negocio (LOB).
  
**output.cs**  
El archivo de salida predeterminado creado por la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe).  
  
## <a name="p"></a>P  
  
**sondeo**  
Una técnica que utilizan controladores de dispositivo para averiguar desde varios dispositivos si contienen datos que se va a transmitir. Los dispositivos están sondeo uno a uno.

**Id. de programa**  
Canal único que se va a enviar una solicitud de cambio en la puerta de enlace configurada. El identificador de programa o nombre de host y el servicio de puerta de enlace SAP, proporcionado para el identificador de programa, deben coincidir con los parámetros de registro (a través de RfcAccept).

**proxy**  
En WCF, hace referencia a un objeto de código administrado que implementa el contrato de servicio expuesto por un servicio. El modelo de servicio WCF se basa en el uso de estos servidores proxy. En el modelo de servicio WCF, el contrato de servicio se expresa como una interfaz. NET.
  
## <a name="r"></a>L  
  
**Llamada a función remota (RFC)**  
Un procedimiento para el intercambio de datos entre un cliente y servidor. Normalmente el cliente llama a un programa de servidor y el servidor devuelve los resultados a través de una conexión TCP/IP.
  
**solicitudes y respuestas**  
Un patrón de intercambio mensajes (MEP) en el que el remitente envía un mensaje de solicitud y espera un mensaje de respuesta con respecto al receptor. En BizTalk Server, MEP se conoce como patrones de comunicación. Dependiendo de la tecnología de mensajería y la dirección del mensaje de solicitud (entrante o saliente), este patrón también se denomina petición-respuesta o solicitud-respuesta.

**experiencia en tiempo de ejecución**  
Los procedimientos y las operaciones realizadas por un desarrollador en tiempo de ejecución o al implementar una solución; Por ejemplo, al crear un enlace de puerto físico desde la consola de administración de BizTalk Server.
  
## <a name="s"></a>S  
  
**esquema**  
Estructura de un mensaje. Un esquema puede contener varios subesquema.
  
**Herramienta de utilidad de metadatos de ServiceModel (svcutil.exe)**  
Una utilidad de línea de comandos que se incluye con WCF. Se utiliza para crear el código de proxy del modelo de servicio de la descripción del servicio (metadatos) que se expone mediante un servicio WCF como un adaptador. Para las operaciones de salida, la herramienta crea un código de clase y la aplicación auxiliar de cliente WCF; para las operaciones de entrada, la herramienta crea un código de aplicación auxiliar de contrato del servicio WCF.

**SOAP (Simple Object Access Protocol)**  
Un protocolo simple basado en XML para intercambiar estructurada y de tipos de información en entornos distribuidos descentralizados. WCF se basa en el intercambio de mensajes SOAP entre clientes y servicios para invocar operaciones y devolver resultados.

**Mensaje SOAP**  
documento XML con formato correcto. Debería utilizar el sobre SOAP y el espacio de nombres de codificación SOAP e incluir una declaración opcional XML, con un sobre SOAP (elemento raíz) compuesto de un encabezado opcional SOAP y un cuerpo de mensaje SOAP.

**SQL Server Integration Services (SSIS)**  
Un componente que se usa para importar, exportar y transformar datos de distintos orígenes de datos. Servicios de transformación de datos (DTS) se ha llamado anteriormente.
  
**datos fuertemente tipados**  
Un conjunto de datos o un conjunto de resultados que está enlazado a un tipo de objeto subyacente. Cada fila de un conjunto de datos XML fuertemente tipados se compone de un tipo, con el nombre de elementos que corresponden a los campos del tipo de objeto subyacente.

  
## <a name="t"></a>T  
  
**transacción TID (Id.)**  
Un identificador único global que SAP se asocia a cada unidad lógica de trabajo (LUW).  
  
 
## <a name="w"></a>W  
  
**Modelo de canal WCF**  
Un modelo de programación que se basa en varias interfaces y otros tipos. Los canales proporcionan un modelo de programación de bajo nivel para enviar y recibir mensajes.
  
**Cliente de WCF**  
Una construcción de aplicación de cliente que expone las operaciones de servicio como métodos. Puede usar el agregar adaptador de servicio de referencia de complemento de Visual Studio o la herramienta de utilidad de metadatos de ServiceModel para generar una clase de cliente WCF desde los metadatos expuestos por un adaptador.

**Contrato de servicio WCF**  
Representación en forma de código administrado del contrato de servicio. Se expresa como una interfaz en las clases y métodos se atribuyen para definir el servicio, la operación, el mensaje y el contratos de datos usados para comunicarse con un servicio. Puede usar la herramienta de utilidad de metadatos de ServiceModel o el agregar adaptador de servicio de referencia de complemento de Visual Studio para generar un contrato de servicio WCF de los metadatos expuestos por un adaptador. Implemente el contrato de servicio WCF para operaciones de recepción de un sistema LOB.

**Modelo de servicio WCF**  
Un modelo de programación de WCF en el que un servicio se representa como un objeto de código administrado. Las operaciones expuestas por el servicio se representan como métodos con datos fuertemente tipados.

**datos débilmente tipada**  
Un conjunto de datos o un conjunto de resultados que no está enlazado a un tipo de objeto subyacente. Cada fila de un conjunto de datos XML débilmente tipada se compone de una colección de columnas genéricas en el que describen los atributos el nombre y tipo de cada elemento.

**Servicios Web**  
Una unidad de lógica de la aplicación que proporcionan datos y servicios a otras aplicaciones. Las aplicaciones obtienen acceso a los servicios Web XML mediante protocolos Web y formatos de datos estándar como HTTP, XML y SOAP, independientemente del modo en que se implementan los servicios Web XML. Los servicios Web XML combinan los mejores aspectos de Internet y del desarrollo basado en los componentes, y son los pilares del modelo de programación Microsoft .NET.

**Lenguaje de descripción de servicios Web (WSDL)**  
Un lenguaje basado en XML que describe un servicio como un conjunto de extremos que operan en los mensajes. El documento WSDL describe el contrato de servicio, contratos de operación, contratos de mensaje y contratos de datos que los clientes deben usar para comunicarse con el servicio.

**Windows Communication Framework (WCF)**  
Una infraestructura de comunicación orientadas a servicios de Microsoft. El marco de trabajo inherentemente proporciona a los clientes con un servicio de programación modelo y un modelo de programación para un control más preciso de intercambios de mensajes de canal.

**Extremo de WS-Metadata Exchange (MEX)**  
Un punto de conexión expuesto por un servicio WCF, por ejemplo, un adaptador que implementa el **IMetadataExchange** interfaz. Un extremo de WS-Metadata Exchange puede usarse para recuperar una descripción de servicio (WSDL) para las operaciones expuestas por un adaptador en el sistema de destino.  
  
## <a name="x"></a>X  
  
**Lenguaje de definición de esquemas XML (XSD)**  
Lenguaje de esquemas. Un esquema XML define los tipos de elementos, atributos y los datos que cumplen con la parte 1 del esquema XML de World Wide Web Consortium (W3C): recomendación de estructuras del lenguaje de definición de esquemas XML. Parte 2 del esquema XML de W3C: la recomendación de tipos de datos es la recomendación para definir los tipos de datos que se utilizan en los esquemas XML. El lenguaje de definición de esquemas XML permite definir la estructura y los tipos de datos de los mensajes XML.