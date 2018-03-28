---
title: Términos y definiciones comunes | Documentos de Microsoft
description: Glosario de términos y y sus significados para BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac9c7c7d-a97e-425a-9666-02ca6edd8be6
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742b695338d7038f830b823af720bd3048399473
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="glossary"></a>Glosario
En la Ayuda de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se usan los términos y definiciones siguientes.  
  
## <a name=""></a>.  
  
|Término|Definición|  
|----------|----------------|  
|archivo .brl|Archivo de definición de reglas de negocios.|  
|archivo .btm|Un archivo de asignación de BizTalk Server.|  
|archivo .btp|Un archivo de canalización de BizTalk Server.|  
|.btproj|Un archivo de proyecto de BizTalk.|  
|archivo .btt|Archivo de perfil de seguimiento.|  
|archivo .odx|Archivo de orquestación de BizTalk Server.|  
|archivo .xsd|Archivo de esquema de BizTalk Server.|  
|||  
  
## <a name="a"></a>A  
  
|Término|Definición|  
|----------|----------------|  
|action|Una o más funciones correspondientes a la parte "ENTONCES" de una regla, que se utiliza para especificar lo que debe hacerse cuando una condición se evalúa como true.|  
|propiedad Activar|Propiedad de la forma Recepción que se utiliza para indicar que la orquestación está activada cuando se recibe un mensaje. La forma Recepción sólo se puede marcar como activada cuando sea la primera forma de envío o de recepción activada de una orquestación.|  
|bloque de activación|Agrupación de pasos o acciones dentro de un modelo de actividad.|  
|recepción de activación|Abreviación para la condición de la forma Recepción cuando la propiedad Activar de esta forma está establecida como True.|  
|modelo de actividad|Secuencia predefinida de acciones. Se puede invocar en bloques de activación.|  
|paso del modelo de actividad|Sinónimo de una acción desde el punto de vista de un modelo de actividad. Cuando la acción se incluye en un modelo de actividad, se le hace referencia como "paso del modelo de actividad".|  
|nodo de actividad|Nodo que contiene los hitos y elementos de datos que representan la información de interés para el analista de negocios, que éste crea mediante los Asistentes para Microsoft Excel.|  
|ventana de actividades|Define el período de tiempo durante el que son visibles los datos de instancia de las actividades. Los datos siempre están cambiando debido a que el punto temporal está siempre cambiando. Una vez que los datos hayan pasado por la ventana de actividades, puede desplazarse hasta la base de datos de archivo de BAM ejecutando el paquete DTS/SSIS de mantenimiento de datos. Tras desplazarse hasta la base de datos de archivo de BAM, dejará de estar disponible para la realización de consultas en el portal de BAM.|  
|actor|Persona o proceso que inicia o participa en una actividad. Los actores pueden ser iniciadores o destinos.|  
|adaptador|Componente basado en COM o .NET que facilita el intercambio de mensajes entre aplicaciones (por ejemplo, un sistema de aplicaciones para negocios) y BizTalk Server. El adaptador consiste en una serie de componentes de tiempo de diseño y de tiempo de ejecución para las operaciones de envío y recepción.|  
|marco de trabajo de adaptadores|Especificaciones para la creación de los adaptadores de BizTalk mediante unos estándares abiertos basados en los servicios Web.|  
|anexo|Parte de un acuerdo Un acuerdo consiste en varios anexos que definen qué proceso empresarial se usa, su función, la función del socio comercial y las directivas o parámetros que se usan en dicha relación, junto con la documentación, como las condiciones legales y económicas.|  
|aplicación afiliada|Entidad lógica del inicio de sesión único empresarial (SSO) definida por el administrador que representa un sistema o subsistema como host, sistema de servidor o aplicación de sistema de aplicaciones al que se conecta mediante el SSO. Una aplicación afiliada puede representar tanto un sistema ajeno a Windows, como un gran sistema (mainframe) o equipo UNIX. También puede representar una aplicación, como SAP o una subdivisión del sistema, como los subsistemas "Beneficios" o "Recibos de pago".|  
|agenda|Lista ordenada de acciones de reglas que va a ejecutar el motor de reglas.|  
|agregación|Tabla o estructura que contiene datos precalculados para un cubo de procesamiento analítico en línea (OLAP). Las agregaciones admiten la realización rápida y eficaz de consultas de una base de datos multidimensional.|  
|acuerdo|Elemento definitorio de una configuración de relaciones. Un acuerdo se basa en el proceso de negocio subyacente y los artefactos de administración de entidades, y se define entre su propio perfil y el perfil de su socio. Consta de uno o varios anexos. Anexos definen el proceso empresarial que se usa, la función de su organización, su socio comercial y los parámetros utilizados en la relación. Los acuerdos también pueden hacer referencia a perfiles de grupos de socios comerciales en lugar de a perfiles de socios comerciales individuales. Esto facilita la administración de socios comerciales que tienen relaciones comerciales idénticas con su organización.|  
|notificación de alerta|Medios utilizados para notificarle a un usuario o grupo de usuarios una situación predefinida específica que podría tener lugar.|  
|alias|Modo alternativo de hacer referencia a una entidad. A todas las entidades se les da un alias único predeterminado con un nombre de organización, un calificador como OrganizationName y el valor del nombre de la entidad. Este alias siempre recibe tratamiento de alias predeterminado. Los alias se proporcionan como tríadas de nombre, calificador y valor. No puede haber dos entidades de la misma base de datos de administración de BizTalk con el mismo par de valor y calificador.|  
|todos, FirstMatch|Dos tipos de modo de ejecución para las fases de canalización. Todos indica la ejecución lineal de los componentes de canalización de la fase. FirstMatch indica una ejecución examinada en la que el primer componente que reconoce el formato de mensaje consume el mensaje. En la ejecución lineal, todos los componentes de una fase se ejecutan por orden antes de que el mensaje se pase a la fase siguiente.|  
|ANSI X.12|Formato de mensaje desarrollado por el American National Standards Institute. X.12 se utiliza principalmente en los EE.UU.|  
|adaptador de aplicaciones|Adaptador creado para funcionar con un protocolo o aplicación en concreto, como SQL.|  
|datos archivados|Datos procesados por BizTalk Server y almacenados en la base de datos correspondiente.|  
|artefacto|Suele hacerse referencia a este elemento como parte de una aplicación de BizTalk, que constituye una unidad lógica para una solución de BizTalk. Los artefactos se administran e implementan mediante la consola de administración de BizTalk Server: Algunos ejemplos son las orquestaciones, las canalizaciones, los esquemas de mensaje, los certificados de seguridad, las directivas de reglas de negocio y los enlaces. Los artefactos también son partes de los proyectos de BizTalk, otra unidad lógica de las soluciones de BizTalk. En este contexto, los artefactos se usan para generar en Visual Studio los ensamblados que componen una solución de BizTalk.|  
|ensamblador|Componente de canalización que combina documentos individuales en un lote. Los componentes de canalización del ensamblador que proporciona BizTalk Server son el ensamblador de archivos sin formato, el ensamblador de BizTalk Framework y los componentes de canalización de ensamblador XML.|  
|ensamblado|Archivo dll que puede contener recursos, como orquestaciones, canalizaciones, esquemas, asignaciones y aquellos recursos que no son específicos de BizTalk Server, que se van a utilizar en una aplicación de BizTalk.|  
|implementación de ensamblados|Proceso de implementación de los recursos de un ensamblado desde Visual Studio en una aplicación de BizTalk.|  
|Asistente para implementar ensamblados|En BizTalk Server 2004, asistente que le guía en los pasos que tiene que llevar a cabo para agregar, quitar, importar y exportar ensamblados; importar y exportar enlaces, e instalar o desinstalar ensamblados de la caché de ensamblados global (GAC). En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], esta funcionalidad no se proporciona por los asistentes para importar, instalar y exportar.|  
|versión de ensamblado|Identificador de un ensamblado, resultado de la combinación de una versión principal y secundaria.|  
|orquestación atómica|Transacción transitoria que exige la activación y desactivación de las semánticas de una transacción ACID (Atomicidad, Consistencia, Aislamiento y Durabilidad) similar a una aplicación COM+ que utiliza el servicio DTC.|  
|atributo|Construcción XML utilizada en XML para asociar la información adicional con los elementos XML.|  
|autenticación de confianza|Medio para marcar cada aplicación indicando que ésta puede enviar mensajes al cuadro de mensajes con un Id. de entidad (PID) diferente del Id. de seguridad de Windows (es decir, no proporcionado por él) de la cuenta de servicio de la instancia de aplicación.|  
  
## <a name="b"></a>B  
  
|Término|Definición|  
|----------|----------------|  
|BAM|Vea Supervisión de la actividad económica (BAM).|  
|actividad de BAM|Lista de extremo a extremo de hitos y datos capturados por BAM para que se supervise una unidad de trabajo. Por ejemplo, una actividad de aplicaciones de préstamo podría contener hitos como "Préstamo aprobado" y datos como" Nombre del candidato" e "Importe del préstamo". Las actividades de BAM se asignan a menudo directamente a un proceso empresarial.|  
|alerta BAM|Notificación que genera la infraestructura de BAM (en concreto, los servicios de notificación de SQL Server) para informar al destinatario de que existe un conjunto de condiciones determinado. Los usuarios definen las condiciones para un alerta y los servicios automatizados generan la alerta siempre que se cumplan las condiciones.|  
|Punto de control de BAM|También conocido como uno de los elementos del complemento de BAM para Excel.|  
|configuración de BAM|Archivo XML que contiene las opciones para que se manifieste BAM, como nombres de servidor y de base de datos de importación principal de BAM.|  
|Definición de BAM|Representación XML de un modelo de observación de BAM.|  
|marco de trabajo de BAM|Conjunto de API que admite infraestructura creada de forma dinámica y concentración de eventos.|  
|infraestructura de BAM|Consta de tablas de SQL Server, vistas de BAM, procedimientos almacenados, paquetes de servicios de transformación de datos (DTS) de la base de datos de BAM (de importación principal, de archivo, de esquema de estrella y de análisis) como se ha configurado y administrado mediante implementaciones incrementales de las definiciones de BAM. La infraestructura es donde, en tiempo de ejecución, se correlacionan, agregan y luego están disponibles los eventos para las consultas de usuario.|  
|administrador de BAM|Componente interno que administra la infraestructura dinámica para la supervisión de la actividad económica.|  
|modelo de observación de BAM|Definición de alto nivel de los requisitos de visibilidad para un proceso empresarial que especifica los eventos de datos e hitos que se van a recopilar (la actividad de BAM), descripción de agregaciones de datos y presentación de la información a los usuarios (la vista de BAM).|  
|vista de BAM|Perspectiva específica de la función de los datos que constituye una actividad de BAM. Las vistas se componen de datos filtrados, agregaciones de los datos filtrados y formas de presentar los datos filtrados, como un informe de tabla dinámica. BAM admite la definición de una o más vistas por actividad.|  
|elemento de datos base|En BAM, elemento de actividad utilizado como base para una dimensión o una medida. Por ejemplo, el elemento de datos base "Id. de producto" se podría utilizar como base para una medida Número (qué cantidad se ha vendido de un producto dado).|  
|enlazar|Proceso por el que se vinculan los componentes y capas de software. Cuando se instala un componente de red, se establecen las relaciones de enlace y dependencias de los componentes. El enlace permite a los componentes comunicarse entre sí. En BizTalk Server, es una asignación establecida entre un extremo válido para los adaptadores de orquestaciones (puerto o vínculo de función) y los extremos físicos específicos de los adaptadores (puertos o entidades de envío y recepción).|  
|archivo de enlace|Archivo que contiene una instantánea del enlace tal y como se veía en ese momento. No contiene detalles sobre el proceso de finalización del enlace con respecto a la orquestación.|  
|Consola de administración de BizTalk|Microsoft Management Console (MMC) que se utiliza para administrar un grupo de BizTalk Server.|  
|Grupo de administradores de BizTalk Server|Grupo que administra a BizTalk Server. Las tareas de administración incluyen el acceso a la cola de suspensión, la actualización de la base de datos de configuración, etc.|  
|aplicación de BizTalk|Grupo de artefactos relacionados, recursos y configuración que se exponen conjuntamente para la administración dentro de la consola de administración de BizTalk Es posible que un artefacto de una aplicación haga referencia a otro artefacto de la misma aplicación, o a un artefacto de cualquier aplicación a la que se hace referencia.|  
|aplicación de BizTalk 1|Aplicación creada de forma predeterminada en cada instalación nueva de BizTalk Server. Esta aplicación se crea principalmente para conservar la compatibilidad con las versiones anteriores. En esta carpeta se muestran los artefactos que se implementaron sin una aplicación especificada. Asimismo, los artefactos nuevos que se implementan sin una aplicación especificada se implementan en la aplicación predeterminada. Cualquier otra aplicación se puede establecer como predeterminada al cambiar la configuración de usuario.|  
|grupo Usuarios de aplicación de BizTalk|Grupo de usuarios que pueden obtener acceso a los cuadros de mensajes de un grupo de BizTalk en concreto.|  
|vista Aplicaciones de BizTalk|Una de las dos vistas (con la vista Implementación de BizTalk) que aparece cuando se abre la consola de System Center Operations Manager para BizTalk Server. Un administrador de BizTalk usa esta vista para supervisar el estado de los artefactos y las aplicaciones de BizTalk, como orquestaciones, puertos de envío y ubicaciones de recepción.|  
|Ensamblado de BizTalk|Archivo DLL de Microsoft Windows que contiene información de recursos, como orquestaciones, canalizaciones, esquemas y asignaciones que se utilizarán en una solución empresarial de BizTalk Server. El ensamblado también contiene el número de versión, la referencia cultural y los tokens de clave pública.|  
|vista Implementación de BizTalk|Una de las dos vistas (con la vista Aplicaciones de BizTalk) que aparece cuando se abre la consola de System Center Operations Manager para BizTalk Server. Un administrador de TI empresarial usa esta vista para supervisar el estado general de la “implementación física” de una configuración de BizTalk Server.|  
|Editor de BizTalk|Una herramienta visual, alojada en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], para construir esquemas de BizTalk Server que pueden definir la estructura de mensajes de instancias formateados en XML y nativos.|  
|Explorador de BizTalk|Ventana de herramientas de Visual Studio que muestra los contenidos de una base de datos de configuración de BizTalk. Muestra elementos como ensamblados, puertos y entidades en un árbol jerárquico. Puede utilizar el Explorador de BizTalk para configurar y administrar los proyectos, entidades y orquestaciones de BizTalk.|  
|Modelo de objetos para el explorador de BizTalk|API que se utilizan para crear herramientas y secuencias de comandos con el fin de automatizar las tareas de implementación posterior que se llevan a cabo en el Explorador de BizTalk. Se puede utilizar el Modelo de objetos para el explorador de BizTalk para tales tareas de posimplementación, como la creación de puertos, el enlace de orquestaciones, la administración de propiedades de entidad o cualquier otra tarea para la que se pudiera utilizar el Explorador de BizTalk. Las API del modelo de objetos de Explorador de BizTalk están en el espacio de nombres Microsoft.BizTalk.ExplorerOM.|  
|BizTalk Framework |Marco de trabajo de comercio electrónico de plataforma neutral basado en los esquemas y la normativa del sector de lenguaje de marcado extensible (XML). El marco de trabajo permite la integración entre empresas y entre sistemas empresariales, independientemente de la plataforma, sistema operativo o tecnología subyacente.|  
|grupo de BizTalk|Grupo que contiene cuadros de mensajes, hosts, ubicaciones de recepción, puertos de envío, grupos de puertos de envío, orquestaciones, servidores y adaptadores.|  
|host de BizTalk|Límite de seguridad y proceso lógico de BizTalk Server. Cada host tiene asignados unos grupos de seguridad y puede contener varias instancias de host, cada una en un equipo individual, que realizan el trabajo del host. A su vez, cada instancia de host pertenece exactamente a un host y la cuenta de servicio de la instancia de host pertenece a los grupos de seguridad del host. Los grupos de seguridad se pueden utilizar para conceder permisos para recursos físicos como, bases de datos que utilizarán las instancias de host en el host.|  
|alerta de Paquete de administración de BizTalk|Notificación a la que los administradores se pueden suscribir del Paquete de administración de BizTalk Server. Después de suscribirse a una alerta determinada, los administradores reciben una notificación cuando se cumplen determinadas condiciones. Por ejemplo, si determinado número de instancias de host están limitadas, se puede producir una alerta.|  
|diagnóstico de paquete de administración de BizTalk|Característica que los administradores pueden usar para ver la causa de un determinado problema y la información para solucionarlo. Por ejemplo, si el estado de un puerto de envío aparece en rojo, la pestaña Evento de cambio de estado de la consola de Operations Manager muestra la razón de que pasara de verde a rojo.|  
|Asignador de BizTalk|Herramienta visual ubicada en Visual Studio para la construcción de asignaciones de BizTalk, que definen las transformaciones de datos.|  
|Message Queue Server de BizTalk|Componente de transporte de colas de mensaje de BizTalk Server. Se incluye como componente interno principal del producto BizTalk Server y es uno de los varios componentes de adaptador de BizTalk Server.|  
|almacén de mensajes de BizTalk|Tabla de Microsoft SQL Server que almacena todos los mensajes y sus componentes. Las orquestaciones que se están utilizando emplean referencias de mensaje incluidas en el almacén para eliminar de la cola una copia del mensaje y sus propiedades del almacén de mensajes.|  
|proyecto de BizTalk|Tipo de proyecto de Visual Studio utilizado para crear aplicaciones que se ejecutan en BizTalk Server.|  
|archivo de proyecto de BizTalk (.btproj)|Archivo que contiene la configuración específica del proyecto de BizTalk.|  
|Sistema de proyectos de BizTalk|Sistema utilizado para crear una parte o la totalidad de una aplicación o solución empresarial de BizTalk Server. Se utiliza para agregar, editar o quitar elementos de BizTalk Server (orquestaciones, asignaciones, esquemas y canalizaciones). Contiene comandos como compile y deploy.|  
|Paquete de administración de BizTalk Server|Mejora de BizTalk que ayuda a garantizar las capacidades de supervisión completas de las aplicaciones e infraestructura de BizTalk. Incluye características como diagnósticos y alertas para ayudar a supervisar el estado de una implementación de BizTalk.|  
|Administración de servidor BizTalk Server|Interfaz de Microsoft Management Console (MMC) usada para administrar el grupo de servidores de BizTalk Server y sus propiedades, así como para supervisar las funciones de recepción y los elementos de trabajo de las colas de Microsoft SQL Server que usa el grupo de servidores.|  
|archivo de asignación de BizTalk Server (.btm)|El formato almacenado de una asignación de BizTalk que creó y compiló el Asignador de BizTalk para generar directivas de transformación de tiempo de ejecución mediante Transformación de lenguaje de hojas de estilo extensible (XSLT).|  
|Asignador de BizTalk|Característica que permite a los usuarios generar visualmente transformaciones entre dos esquemas de una aplicación de BizTalk. También contiene mejoras de uso como ayuda para asignaciones complejas.|  
|motor de mensajería de BizTalk Server|Conjunto de servicios necesarios de un producto de software intermedio para facilitar las soluciones a los escenarios de clientes. Estos servicios de tiempo de ejecución son una parte esencial de la plataforma de BizTalk Server. Entre estos servicios, se encuentra el procesamiento de canalizaciones ejecutantes de mensajes. El procesamiento de canalizaciones proporciona normalización de formato de datos y extracción de propiedades.|  
|archivo de canalización de BizTalk Server (.btp)|Archivo que describe la configuración de la canalización y los componentes que hay dentro de ella. Este tipo de archivo puede compilarse como parte de un proyecto de BizTalk.|  
|esquema de BizTalk Server|Definición basada en el Lenguaje de definición de esquemas XML (XSD) de la estructura de uno o más mensajes de instancia de BizTalk Server.|  
|archivo de esquema de BizTalk Server (.xsd)|Archivo que contiene el formato almacenado de un esquema de BizTalk.|  
|Panel de configuraciones de BizTalk|Característica de BizTalk que los administradores de BizTalk pueden usar para administrar y modificar centralmente la configuración del motor de BizTalk. Los administradores pueden exportar la configuración de un entorno a otro, así como importarla; por ejemplo, de fase a producción.|  
|parte del cuerpo|Vea parte del cuerpo de mensaje.|  
|BTSTask|Herramienta de línea de comandos que le permite administrar aplicaciones y ensamblados. Puede utilizar BTSTask para agregar aplicaciones de BizTalk a la base de datos de administración de BizTalk, agregar un recurso a una aplicación, exportar una aplicación a un archivo MSI, exportar información de enlace a un archivo, importar una aplicación desde un archivo MSI, importar información de enlace desde un archivo, enumerar todos los recursos de una aplicación, enumerar todas las aplicaciones de la base de datos de administración de BizTalk, enumerar los contenidos de un archivo MSI, quitar una aplicación de la base de datos de administración de BizTalk y de la consola de administración de BizTalk, y quitar un recurso de una aplicación.|  
|Supervisión de la actividad económica (SAE)|Característica de BizTalk Server que proporciona a los usuarios empresariales una vista en tiempo real de sus procesos empresariales heterogéneos, lo que les permite tomar importantes decisiones empresariales.|  
|vista Actividad económica|Conjunto jerárquico de vistas que muestra los procesos empresariales y que se utiliza para definir el modo en que una categoría específica de usuarios empresariales desean ver la actividad empresarial. Puede que haya más de una forma de interpretar los mismos datos de actividad empresarial (seguimientos de BAM).|  
|analista de negocios|Usuario que posee conocimientos de análisis económico y de administración empresarial. La responsabilidad principal del analista de negocios es utilizar datos de nivel empresarial y analizarlos para las tendencias empresariales.|  
|usuario final de negocios|Trabajador de información responsable de la supervisión y solución de problemas de un proceso empresarial o del intercambio de mensajes empresariales. No tiene por qué tratarse de un técnico.|  
|Servicios de configuración de procesos empresariales|Herramientas que permiten que los usuarios empresariales configuren y administren los elementos de orquestación de nivel bajo mediante directivas empresariales. Los programadores y fabricantes independientes de software utilizan estas herramientas para definir procesos empresariales de forma que se puedan configurar utilizando parámetros y directivas empresariales.|  
|área de trabajo de procesos empresariales|Interfaz que permite que los gestores empresariales administren y lleven a cabo un seguimiento de los procesos empresariales desde SharePoint Team Services.|  
|perfil de negocio|Fisonomía de negocio de una organización. Cada división de negocio de una organización que comercializa con otra división de negocio de otra organización se representa como un perfil de negocio en una solución de administración de socios comerciales (TPM). Todas las propiedades que definen los parámetros de mensajería de negocio a negocio específicos de la división de negocio, unidad de negocio o sistema de negocio se capturan en su perfil de negocio.|  
|herramienta de Compositor de reglas de negocios|Herramienta gráfica de interfaz de usuario utilizada para componer directivas.|  
|Motor de reglas de negocios|Motor de inferencia de tiempo de ejecución que evalúa reglas con respecto a eventos e inicia acciones en función de los resultados de tal evaluación.|  
|Lenguaje de reglas de negocios|Lenguaje de marcado de reglas en formato XML para definiciones de reglas declarativas.|  
|negocio a negocio|Hace referencia a la categoría de ventas relacionada con transacciones y actividades relacionadas entre una empresa y los compradores que no son los consumidores, como cuerpos gubernamentales, compañías y distribuidores. Se refiere a una empresa que se comunica con otra o a la que le vende productos.|  
  
## <a name="c"></a>C  
  
|Término|Definición|  
|----------|----------------|  
|duración calculada|Propiedad que permite que el usuario utilice una fórmula personalizada para las columnas calculadas.|  
|lista de códigos|Conjunto de pares de abreviaciones o explicaciones utilizadas como una ayuda de tiempo de ejecución para proporcionar conjuntos de valores de enumeración de Lenguaje de definición de esquemas XML (XSD).|  
|herramienta de implementación de líneas de comandos|Herramienta utilizada para agregar, quitar, importar y exportar ensamblados, importar y exportar enlaces e instalar o desinstalar ensamblados de la caché de ensamblados global (GAC).|  
|confirmación de solicitudes de cambio|Vea otro término: solicitud de cambio de tipo de extremo|  
|patrón de comunicación|Propiedad que determina si la comunicación del puerto es unidireccional o bidireccional (solicitud-respuesta).|  
|compensation|Grupo de acciones designadas para deshacer o mitigar el efecto de una transacción ejecutada.|  
|ficha Compensación|Superficie de diseño utilizada para agregar compensaciones a las orquestaciones.|  
|compilar|En el contexto de BizTalk Server, proceso de conversión de la representación en tiempo de diseño de los elementos de BizTalk Server, como esquemas, asignaciones y orquestaciones, en sus equivalentes en tiempo de ejecución, almacenados en los ensamblados de Visual Studio.|  
|servicio de composición|Componente que controla la activación de acciones, la funcionalidad de interrupción y el envío de respuestas de tarea. El servicio compone los mensajes de protocolos de acción y los envía a los agentes de escucha HTTP que, luego, los enrutan hacia la base de datos de cuadro de mensajes de BizTalk para su utilización.|  
|condición|Parte "SI" de una regla utilizada para especificar qué condiciones deberían evaluarse, es decir, representarse mediante una expresión lógica única que evalúa como true o false. Una condición es extensible para admitir condiciones definidas por el usuario.|  
|intervalo de actualización de la caché de configuración|Intervalo, medido en segundos, en el que se recogen las modificaciones de las propiedades generales para un grupo de BizTalk, como el host SMTP. Este intervalo se establece como parte de la configuración de grupos. Cuando inicia BizTalk Server, se almacenan todos los elementos de la administración de BizTalk Server, como bases de datos de cuadro de mensajes, propiedades de servidor, adaptadores y conexiones a la base de datos de seguimiento, en la caché de administración. De forma predeterminada, todos los elementos de la caché se actualizarán cada 60 segundos, excepto para las conexiones de bases de datos de servidor y propiedades de servidor.|  
|nombre del servidor de la base de datos de configuración |elemento de interfaz de usuario. Nombre del servidor en el que se aloja la base de datos de configuración o administración.|  
|conector|Servicio de comunicaciones utilizado para intercambiar documentos con los socios comerciales o los sistemas internos.|  
|punto de conexión|Elemento del Diseñador de orquestaciones que permite que el usuario conecte una forma Envío/Recepción con la operación de un puerto.|  
|restricción|Propiedad que restringe al iniciador de los destinos y la acción raíz para realizar cualquier otra acción incluida en el modelo de actividad.|  
|enrutamiento por contenidos|Enrutamiento de un documento en función de la información extraída de la carga del documento. En BizTalk Server, se lleva a cabo el enrutamiento por contenidos mediante la promoción de propiedades de documento y expresiones de filtro de las orquestaciones y puertos de envío.|  
|continuación|Capacidad de contribuir a una única actividad de BAM desde diferentes aplicaciones usando dos identificadores únicos diferentes, como ActivityID. Por ejemplo, en una parte de un proceso de negocio, se puede usar un número de PO para hacer un seguimiento de una actividad. En otra parte del proceso, se puede usar un número de cumplimiento de pedido interno para hacer el seguimiento de la misma actividad. Puede habilitar la continuación y relacionar el número de PO y el número de cumplimiento de pedido, para que ambas partes del proceso puedan agregar información a la misma actividad.|  
|token de continuación|Elemento de información exclusiva que se envía fuera de Aplicación 1.|  
|tipo de conversión|Multiplicador utilizado para convertir la moneda base del sitio Web a la moneda del comprador o del proveedor. El tipo de conversión se almacena en SDK Order Sitelet sólo para fines ilustrativos y un sistema de contabilidad o de realización tercero debería realizar su seguimiento en sitios Web de producción.|  
|correlation|Proceso de hacer coincidir un mensaje entrante con la instancia adecuada de una orquestación. Esta coincidencia se produce mediante propiedades del mensaje que lo vinculan con la orquestación. En los casos en que los mensajes relacionados con el mismo proceso de negocio contienen propiedades incompatibles, como un esquema de pedido con un elemento POId, y el esquema de factura que le acompaña con un elemento OrderID, los programadores consiguen la correlación creando esquemas de propiedad que contienen nombres de propiedad abstractos para esos elementos.|  
|Id. de correlación|Id. generado aleatoriamente que se asocia con un mensaje y se pasa junto a él mientras exista.|  
|conjunto de correlaciones|Instancia de un tipo de correlación, es decir, las propiedades enumeradas de un mensaje que se utilizan para determinar si pertenece a una instancia en concreto de una orquestación.|  
|tipo de correlación|Conjunto de propiedades de mensaje que identifican únicamente un proceso empresarial y que se utilizan para correlacionar mensajes con instancias de orquestación.|  
|referencia cultural|Propiedades localizables y de lenguaje de texto y datos.|  
|adaptador personalizado|Un fragmento de código personalizado que escribe un programador y lo coloca antes de una canalización de recepción o después de una canalización de envío para establecer una conexión con los adaptadores o las aplicaciones.|  
|números personalizados|Serie de números asignados por un contador que aumenta en uno el valor de cada uno de ellos.|  
|referencia cíclica|Patrón de un esquema XML en el que se declara que un nodo descendiente es del mismo tipo complejo que uno de sus nodos antecesores y crea, por lo tanto, un esquema que representa mensajes de instancia con profundidad potencialmente ilimitada.|  
  
## <a name="d"></a>D  
  
|Término|Definición|  
|----------|----------------|  
|DDL (Lenguaje de descripción de datos)|Lenguaje utilizado para definir datos y sus relaciones con respecto a otros datos. Se utiliza para crear la estructura de datos de una base de datos. Los sistemas de administración de bases de datos principales (DBMS) utilizan un lenguaje de descripción de datos SQL.|  
|dimensión de datos|Nodo específico creado en la vista jerárquica del Editor de perfiles de seguimiento como elemento secundario inmediato del perfil de seguimiento específico para describir una agrupación lógica o dimensión de datos. Cada dimensión de datos se nombra de forma única y se compone de uno o más campos de datos.|  
|elemento de datos|Nodo específico creado en la vista jerárquica del Editor de perfiles de seguimiento que es elemento secundario directo de la categoría de datos. El campo de datos existe como campo específico de la carga empresarial.|  
|asignación de datos|Proceso de tiempo de diseño de definición de una asignación entre los nodos de un esquema de origen y los de un esquema de destino.|  
|DDL|Vea Lenguaje de descripción de datos.|  
|host predeterminado|Objetos de administración que facilitan la implementación y el alta de orquestaciones. Estos objetos se identifican en la consola de administración de BizTalk Server porque llevan una marca de verificación. Durante el proceso de alta de orquestación, se utiliza automáticamente el host predeterminado para alojar la orquestación, a menos que el usuario seleccione explícitamente un host diferente.|  
|canalizaciones predeterminadas|Ensamblados de BizTalk Server compilados e implementados que contienen canalizaciones con fases y componentes configurados previamente.|  
|deshidratar|Guarda en el almacén permanente el estado de una orquestación que se esté ejecutando y la quita de la memoria cuando haya estado inactiva durante un período determinado de tiempo.|  
|archivo sin formato delimitado|Tipo de formato de archivo utilizado para representar documentos empresariales en los que los registros y campos estén delimitados por caracteres específicos o secuencias de caracteres.|  
|delimitador|Uno o más caracteres especiales que se utilizan para separar elementos asociados de una estructura delimitada en cualquier nivel (campos, registros, etc.).|  
|degradación|Acto de escribir los datos de fecha y hora de una propiedad de contexto en la carga de documentos.|  
|Base de datos de destino|Único destino admitido, en caso de que se instale con BizTalk Server, aunque se admitirán múltiples bases de datos de destino en la infraestructura del servicio de bus de eventos BAM.|  
|esquema de destino|Esquema utilizado en una asignación de BizTalk Server que representa la estructura de las instancias de mensajes de salida.|  
|DTE (Entorno de herramientas de desarrollo)|Conjunto de interfaces que permiten que los programadores puedan llevar a cabo de forma programada varias de las tareas principales que se pueden realizar desde el entorno de desarrollo integrado (IDE).|  
|jerarquía de dimensión|Estructura lógica de árbol que organiza los miembros de una dimensión para que cada uno de ellos tenga un miembro primario y cero o más miembros secundarios.|  
|nivel de dimensión|Elemento que indica que un conjunto de elementos de datos tienen que considerarse como niveles de una jerarquía de dimensión. Resultados de definición DataPerspective de una jerarquía de dimensión OLAP.|  
|componente de canalización de desensamblador|Componente de canalización que divide los mensajes de un lote en documentos individuales. Los componentes de canalización de desensamblador que proporciona BizTalk Server son: plano Desensamblador de archivo, Desensamblador de BizTalk Framework y desensamblador XML.|  
|campo distinguido|Miembro de clase .NET o campo de esquema del Lenguaje de definición de esquema XML (XSD) de un mensaje que está disponible explícitamente para que una orquestación lo use en expresiones y componentes de canalización personalizada como campo de propiedad escrito. No se puede usar en expresiones de filtro.|  
|coordinador de transacciones distribuidas (DTC)|Servicio integrado con COM+ que hace funcionar las transacciones distribuidas.  El DTC hace posible escalar las transacciones de uno o varios equipos sin que sea necesario un código especial.|  
|DMZ|zona desmilitarizada. Vea Red perimetral.|  
|documento|En EDI, conjunto de segmentos combinados lógicamente. Tipos de documentos incluyen: facturas, pedidos de transporte, declaraciones aduaneras y así sucesivamente.|  
|definición de tipo de documento (DTD)|Una de las varias formas de las que se puede describir la estructura de un documento XML. BizTalk Server puede abrir un esquema descrito mediante un archivo DTD, pero lo convierte a XSD en el proceso.|  
|DTC|Vea Coordinador de transacciones distribuidas.|  
|DTD|Vea Definición de tipo de documento (DTD).|  
|DTE|Vea Entorno de herramientas de desarrollo (DTE).|  
|duration|Elemento que insta al compilador de BAM a crear una columna adicional en la vista que represente la duración entre puntos de control.|  
|adaptador dinámico|Adaptador que tiene una interfaz de usuario personalizada.|  
|enlace dinámico|Enlace de puerto que se aplica al puerto en tiempo de ejecución, normalmente derivado de una propiedad de mensaje como una dirección Responder a.|  
|actualización dinámica de directivas|La recuperación de tiempo de ejecución de directivas mediante el Servicio de actualización de motor de reglas.|  
|puerto dinámico|Puerto de envío que no tiene dirección de destino ni tipo de adaptador asociado con él. Un puerto de envío dinámico permite la asociación de éste con la dirección de destino y el tipo de adaptador en tiempo de ejecución, lo que proporciona flexibilidad en la utilización del mismo puerto de envío para el envío de mensajes a diferentes destinos mediante tipos de adaptador diferentes.|  
  
## <a name="e"></a>E  
  
|Término|Definición|  
|----------|----------------|  
|ENRUTAMIENTO|Vea Intercambio electrónico de datos.|  
|EDIFACT|Vea Intercambio electrónico de datos para administración, comercio y transporte (EDIFACT).|  
|sintaxis EDIFACT UNOA|Sintaxis EDIFACT que permite a los siguientes caracteres: letras mayúsculas, todos los dígitos, espacio en blanco, signo de admiración (!), comillas dobles ("), signo de porcentaje (%)," y "comercial (&), la apertura y el paréntesis de cierre ("("y")"), asterisco (*), coma, guión (-), punto decimal (.), barra diagonal (/), punto y coma (;), menos-de inicio de sesión (\<) y versiones posteriores: de inicio de sesión (\>).|  
|sintaxis EDIFACT UNOB|Sintaxis EDIFACT que permite a los siguientes caracteres: letras mayúsculas y minúsculas, todos los dígitos, espacio en blanco, signo de admiración (!), comillas dobles ("), signo de porcentaje (%)," y "comercial (&), la marca de comillas simples ('), de apertura y cierre de paréntesis ("(" y ")"), asterisco (*), signo más (+), coma, guión (-), punto decimal (.), reenviar barra diagonal (/), dos puntos (:), punto y coma (;), menor-que el inicio de sesión (\<), signo de igual (=), mayor-de inicio de sesión (\>) y el signo de interrogación (?).|  
|EIF|Vea Archivo de entrada del motor (EIF).|  
|EIP|Vea Plataforma de integración de empresas (EIP).|  
|Intercambio electrónico de datos (EDI)|Intercambio electrónico de documentos estructurados y normalizados entre dos aplicaciones informáticas, con la utilización de un conjunto de estándares para controlar la transferencia de documentos, por ejemplo, pedidos y facturas, entre equipos.|  
|Intercambio electrónico de datos para la administración, el comercio y el transporte (EDIFACT)|Intercambio electrónico de datos mundial (EDI)|  
|elemento|En EDI, el nivel mínimo de información de un documento. Por ejemplo, número de factura. En XML, construcción XML que se utiliza para organizar la información de una forma jerárquica anidando algunos elementos dentro de otros a una profundidad potencialmente ilimitada.|  
|grupos de elementos|Estructura de agrupaciones de elementos del mismo nivel en un documento XML según las restricciones de diferentes: orden secuencia (grupo de secuencias), secuencia desordenada (todos los grupos) y uno de varios (grupo de elecciones).|  
|acuerdo de codificación|Acuerdo entre dos perfiles de negocio de dos socios comerciales de usar un protocolo de codificación específico (X12 o EDIFACT) al intercambiar mensajes.|  
|protocolo de codificación|Protocolo que rige la estructura y el contenido de un mensaje de negocio a negocio. La configuración del protocolo de codificación para un perfil de negocio define el protocolo de codificación que una división de negocio usa para enviar y recibir mensajes de negocio a negocio. Algunos ejemplos de protocolo de codificación son X12, EDIFACT, HIPAA y EANCOM.|  
|clave de cifrado|Cadena que se utiliza para cifrar o descifrar la información de credenciales.|  
|solicitud de cambio de tipo de finalización|Última fase de la implementación de un tipo de artefacto en un equipo de destino, durante una importación de un archivo MSI de aplicación de BizTalk mediante la consola de administración o BTSTask. También recibe el nombre de confirmación de solicitudes de cambio o confirmación de un tipo de artefacto.|  
|extremo|Representación lógica de una ubicación, expresada normalmente en formato URL, que proporciona una dirección física para los datos enviados o recibidos.|  
|Archivo de entrada del motor (EIF)|Versión compilada de un esquema de documento. El EIF se utiliza para expedir traducciones y distribuirlas entre otros usuarios de un grupo de usuarios cerrado. Se compila de forma automática cada vez que se genera o edita un esquema de Lenguaje de definición de esquemas XML (XSD) mediante BizTalk Server.|  
|dar de alta|Proceso en el que se asocia una orquestación al entorno físico en el que se ejecutará. Esto incluye especificar los adaptadores que se necesitan para transportar mensajes a la orquestación y desde ésta, el proceso de aplicación en el que se aloja la orquestación y se crean las suscripciones de cuadro de mensajes que indicó el enrutamiento.|  
|integración de aplicaciones de negocios|Proceso de enlace de datos o de una función desde una aplicación empresarial con los de otra aplicación.|  
|Vea Plataforma de integración de empresas (EIP)|Entorno en el que se produce la integración de aplicaciones de empresas. Este escenario es en realidad una clase de escenarios agrupados como único escenario.|  
|sistema de inicio de sesión único empresarial (SSO)|Base de datos de SSO, servidor secreto principal y uno o más de un servidor de inicio de sesión único empresarial (SSO). Estos servidores llevan a cabo la asignación entre las credenciales de Windows y las ajenas a éste, buscan las credenciales en la base de datos de SSO y se utilizan para administrar el sistema SSO. La base de datos de SSO también se utiliza como almacén de configuración para guardar los datos de las configuraciones personalizadas de los adaptadores.|  
|sobre|Conjunto estructurado de información que envuelve y acompaña a un mensaje de instancia y que suele describir información de procesamiento y entrega. Los sobres se pueden anidar.|  
|esquema de sobres|Tipo de esquema que especifica la estructura de un sobre mediante varias propiedades adicionales específicas de los sobres y que proporcionan información específica, como la identificación de contenidos del sobre en una secuencia de datos con doble cifrado.|  
|ciclo de ejecución|Aserción de hechos, evaluación de condiciones y ejecución de acciones incluidas en el motor de reglas de negocios.|  
|Modo de ejecución|Propiedad de la fase de canalización que determina el patrón de ejecución de los componentes de canalización de una fase. El modo de ejecución se puede establecer como Todos o FirstMatch. En el modo Todos, todos los componentes incluidos en la fase se procesan en el orden configurado. Este modo se utiliza cuando se necesitan varios componentes para completar una tarea lógica en concreto y todos ellos tienen que ejecutarse. Si alguno de los componentes se topa con un error al procesar un mensaje que esté pasando a través de esta fase de canalización, se produce un error de tiempo de ejecución.|  
|Asistente para exportación|Asistente que se inicia desde la consola de administración de BizTalk para generar un archivo MSI desde una aplicación de BizTalk. Puede copiar este archivo MSI a una instancia distinta de BizTalk Server y utilizar el Asistente para importación para importar los recursos del archivo MSI.|  
|entrega urgente|Tipo de entrega de mensajes que implica persistencia (almacenamiento en la base de datos de SQL) para los mensajes entrantes y salientes.|  
|Transformación de lenguaje de hojas de estilo extensible (XSLT)|Desarrollado a partir del estándar original Lenguaje de hojas de estilo extensible (XSL). XSL especifica una definición de lenguaje para la presentación de datos XML y para las transformaciones de datos. Presentar los datos significa mostrarlos en algún formato o medio. Está relacionado con el estilo. Transformar los datos hace referencia a analizar un documento XML entrante en un árbol de nodos y, después, convertir el árbol original en un árbol de resultados. La transformación está relacionada con el intercambio de datos.|  
|formato de mensaje externo|Formato del mensaje antes o después de que lo haya procesado BizTalk Server. A veces, el término formato de "cable" también se utiliza para hacer referencia al formato de mensaje externo.|  
  
## <a name="f"></a>F  
  
|Término|Definición|  
|----------|----------------|  
|faceta|Concepto de Lenguaje de definición de esquemas XML (XSD) para restringir los posibles valores que puede adquirir un elemento o atributo, que proporciona parámetros de validación para las instancias de un esquema. Por ejemplo, se puede especificar una longitud mínima y máxima para los datos de cadena. Se aplican diferentes tipos de aspectos a los diferentes tipos de datos.|  
|hecho|Datos de usuario a los que se aplican las condiciones de reglas. En tiempo de ejecución, un hecho es una referencia a los datos.|  
|base de hechos|Colección de hechos con respecto a los cuales se evalúan las condiciones de reglas.|  
|administrador de almacenes de datos (motor de reglas)|Componente complementario opcional y definido por el usuario que implementa una interfaz IFactRetriever para que pueda recopilar hechos a largo plazo que utilizarán las directivas empresariales.|  
|almacén de hechos|Base de datos que almacena información, incluida función y atributos, sobre los actores. El almacén de datos también proporciona exploración de jerarquía de forma que las acciones puedan determinar la posición relativa de los actores incluidos en una organización.|  
|administrador de almacenes de datos|Componente que recupera la información de hechos de los varios objetos FactRetriever.|  
|transporte de conmutación por error|Transporte secundario.|  
|acuerdo de socio comercial de reserva|Colección de configuraciones que BizTalk Server usa para el control de mensajes de negocio a negocio, cuando no existe ningún acuerdo explícito.|  
|Adaptador de archivo|Adaptador que puede leer mensajes del sistema de archivos y que los envía al servidor. El adaptador de archivo también escribe mensajes del servidor en un archivo en el sistema de archivos.|  
|propiedad Expresión de filtro|Propiedad de una forma Recepción que determina qué mensajes se pueden recibir. La forma Recepción debe tener una propiedad Activar establecida como True para tener una expresión de filtro.|  
|vista Buscar mensaje|Vista de informe que permite que los usuarios encuentren los mensajes en función de las propiedades de mensaje de las que se llevó a cabo un seguimiento.|  
|Adaptador de FTP|Adaptador que permite el intercambio de archivos entre BizTalk Server y los servidores FTP.|  
|function|Abstracción que se utiliza para obtener acceso a los miembros de clase de las definiciones de predicado y acción. Se utiliza una función en las acciones y como condición de un predicado.|  
|functoid|Módulo ejecutable que lleva a cabo un cálculo en concreto o una manipulación de datos, y que se utiliza gráficamente al construir asignaciones de BizTalk Server para proporcionar la base para transformaciones más detalladas de las que proporciona XSLT de por sí.|  
|Functoid IntelliSense|Funcionalidad del asignador de BizTalk en la que se proporcionan indicaciones visuales en la superficie de cuadrícula, cuando hay errores en la configuración de functoid.|  
|cuadro de herramientas de functoids|Ventana acoplable de Visual Studio que funciona como paleta de functoids disponibles para su utilización durante la construcción de asignaciones. Los functoids se organizan en fichas diferentes del cuadro de herramientas en función del objetivo que persigan.|  
  
## <a name="g"></a>G  
  
|Término|Definición|  
|----------|----------------|  
|GAC|Vea Caché de ensamblados global.|  
|caché global de ensamblados (GAC)|Contenedor de un servidor BizTalk Server para un grupo que guarda los mismos ensamblados que se implementan en la base de datos de configuración de dicho grupo.|  
|puerto global|Nombre descriptivo utilizado para asociar un puerto a un perfil de socio comercial.|  
|encabezado de grupo|En EDI, parte del mensaje que se utiliza para indicar el inicio de un grupo funcional de documentos.|  
|configuración de nivel de grupo|Uno de los valores que los administradores de BizTalk puede modificar en el panel de configuración de BizTalk. Son ejemplos las propiedades como el intervalo de actualización de configuración, el tamaño máximo de lote de mensajes y el seguimiento de nivel de grupo.|  
|finalizador de grupo|En EDI, parte del mensaje que se utiliza para indicar el fin de un grupo funcional de documentos.|  
|Segmento GS|En EDI, segmento de encabezado de grupo funcional de un conjunto documentos ANSI X.12 (conjuntos de transacciones) del mismo tipo de documentos. Este segmento necesario contiene información sobre un grupo de conjuntos de transacciones de intercambio, como el código de remitente de la aplicación, el código de recepción de la aplicación, número de control del grupo, Id. de sector o versión, etc.|  
  
## <a name="h"></a>H  
  
|Término|Definición|  
|----------|----------------|  
|Controlador|Instancia de un host de BizTalk Sever en el que se está ejecutando un adaptador.|  
|hash|Resultado de tamaño fijo obtenido al aplicar una función matemática unívoca (a veces llamada algoritmo de hash) a una cantidad de datos arbitraria. Si cambia los datos de entrada, se cambia el hash. Se puede utilizar hash en muchas operaciones, como la autenticación y la firma digital. También recibe el nombre de síntesis del mensaje.|  
|supervisión de estado|Proceso de supervisión de aplicaciones, componentes y servidores en los que implementa una solución de BizTalk Server con la finalidad de adelantar o solucionar problemas.|  
|cubo de supervisión de estado|Cubo de procesamiento analítico en línea (OLAP) que contiene información sobre mensajes y servicios. Los dos cubos incluidos con BizTalk Server son: mensajes y servicios.|  
|vista jerárquica|Panel izquierdo del Editor de perfiles de seguimiento (TPE) y área en la que se crean los espacios de nombres de información y las vistas Actividad económica. El objetivo principal es la representación del perfil de seguimiento.|  
|base de datos de historial|Base de datos back-end específica del escenario de administración de procesos empresariales.|  
|host|Contenedor lógico que representa una o más instancias de tiempo de ejecución de BizTalk Server. Es el espacio de procesos en el que reside la información sobre artefactos (es decir, todas las orquestaciones, esquemas, ubicaciones de recepción y adaptadores incluidos en un host). El host también funciona como dominio de seguridad de Windows y representa un límite de proceso virtual dentro del cual se ejecutan las instancias de host en uno o más servidores.|  
|instancia de host|Servicio de Windows NT. Una instancia de host es la representación física de un host en un servidor específico.|  
|configuración de nivel de instancia de host|Uno de los valores que los administradores de BizTalk puede modificar en el panel de configuración de BizTalk. Son ejemplos la configuración y las propiedades de .NET CLR relacionadas con una limitación de memoria de orquestación. Específico de una instancia determinada de host, la configuración de nivel de host rige esencialmente el uso de los recursos de un equipo (por ejemplo, la RAM o E/S). Un ejemplo es el Max. Subprocesos de E/S.|  
|configuración de nivel de host|Uno de los valores que los administradores de BizTalk puede modificar en el panel de configuración de BizTalk. Son ejemplos el seguimiento de host y las propiedades relacionadas con la limitación basada en recursos, la limitación basada en la tasa y la limitación de orquestación. La configuración de nivel de host afectan a la manera en que todas las instancias de host se comportan en una implementación determinada. Por ejemplo, si para Host1 el valor máximo. subprocesos del motor se cambia a 200, todas las instancias de Host1 funcionarán con un máximo de 200 subprocesos del motor.|  
|equilibrio de carga de host|Proceso de agregar varios servidores que ejecutan BizTalk Server a un grupo de BizTalk y luego configurar varias instancias de un host de tipo En curso para que se ejecute en estos servidores. Este procedimiento distribuye la ejecución de servicios y artefactos configurados en ese host entre varias instancias del host, lo que mejora la disponibilidad y escala.|  
|tipo de host|Propiedad que determina si el host se controla dentro o fuera del proceso de BizTalk Server. Los tipo de host son En curso o Aislado.|  
|adaptador de HTTP|Adaptador que permite el intercambio de mensajes entre BizTalk Server y cualquier aplicación que utilice el protocolo HTTP o HTTPS.|  
  
## <a name="i"></a>I  
  
|Término|Definición|  
|----------|----------------|  
|IDE|Vea Entorno de desarrollo integrado.|  
|Importar/Exportar|En el panel de configuración de BizTalk, importar y exportar la configuración y enlaces. La configuración actual de BizTalk para grupo, host e instancia de host se exporta y guarda como archivo XML. Los administradores de BizTalk importan esta configuración para aplicarla en otro entorno de BizTalk.|  
|Asistente para importación|Asistente que se inicia desde la consola de administración de BizTalk para importar recursos desde una archivo MSI a una aplicación de BizTalk. Si la aplicación especificada no existe, el Asistente para importación la crea automáticamente.|  
|composición independiente|Secuencia de dos acciones en la que la segunda acción no depende de un mensaje sincronizado de la primera acción hasta que la segunda acción comienza el procesamiento de la lógica de negocios; la segunda acción puede empezar inmediatamente.|  
|infotip|Información sobre herramientas usada para proporcionar una descripción para comandos del escritorio, la ventana y el menú Inicio, en vistas web y en la columna de comentarios del Explorador de Windows cuando se usa la vista Detalles.|  
|heredero|En el servicio Web de administración de socios comerciales (TPM), concepto que indica que un perfil de miembro heredará todas las preferencias de su grupo primario. En caso de que se trate de un grupo no heredero, el perfil de miembro no heredará ninguna preferencia del grupo primario. Un grupo no heredero puede cambiar a heredero, pero no es posible la operación inversa.|  
|orquestación interrumpible|Orquestación que se puede interrumpir a mitad de proceso en puntos bien definidos.|  
|host de tipo En curso|Tipo de host que funciona dentro del espacio del proceso de BizTalk Server. Cualquier orquestación se puede dar de alta en un host de tipo En curso y éste puede alojar cualquier controlador de envío. Los hosts de tipo En curso únicamente pueden alojar controladores de recepción de host para hosts de tipo En curso (adaptador File).|  
|adaptador de recepción de tipo En curso|Adaptador alojado en los procesos de BizTalk Server. Creados, controlados y destruidos por los procesos de servidor.|  
|Asistente para instalación|Asistente que se puede iniciar durante el paso final del Asistente para importación para instalar una aplicación de BizTalk en un equipo local.|  
|actividad de instancias|Serie de pasos contiguos de procesamiento a través de los cuales fluyen uno o más mensajes.|  
|mensaje de instancia|Unidad discreta de datos de tiempo de ejecución que fluyen a través de BizTalk Server y que normalmente representa un documento empresarial en concreto como, por ejemplo, un pedido. Se diferencia del esquema de BizTalk Server que define su estructura.|  
|Entorno de desarrollo integrado (IDE)|Conjunto combinado de herramientas de interfaz de usuario basadas en Microsoft Windows para crear, probar y refinar una plataforma y sus características.|  
|interceptor|Mecanismo utilizado para extraer datos de las transmisiones de procesamiento y guardarlos en el almacén.|  
|intercambio|En EDI, combinación lógica de documentos. Los intercambios se dirigen a un destinatario único. En la mensajería de BizTalk, un intercambio es un cuerpo de datos procesado por la fase desensamblado de una canalización de recepción o por la fase de ensamblado de una canalización de envío. El intercambio puede contener mensajes o no. En una canalización de recepción, el desensamblador extrae los mensajes contenidos en el intercambio que recibió y propaga estos mensajes a la canalización de recepción.|  
|encabezado de intercambio|En EDI, parte del intercambio, o grupo de documentos asociados lógicamente, que se utiliza para indicar su inicio.|  
|finalizador de intercambio|En EDI, parte del intercambio, o grupo de documentos asociados lógicamente, que se utiliza para indicar su fin.|  
|adaptador intergroup|Adaptador de BizTalk Server destinado a la comunicación intranet/LAN entre dos grupos de BizTalk Server sin requerir almacenamiento intermedio.|  
|formato de mensaje interno|El formato del mensaje después de o antes de que se procesa por BizTalk Server. Por ejemplo, si BizTalk Server recibe un mensaje en el inicio de la canalización de recepción, en formato externo. Después de que el mensaje pase a través de la canalización, se encuentra en formato interno.|  
|host aislado|Tipo de host que funciona fuera de la instalación de BizTalk Server. Un host aislado no puede tener orquestaciones dadas de alta en él, alojar un controlador de envío, utilizar el seguimiento de hosts o utilizarse como host predeterminado del grupo. Sólo los controladores de recepción de hosts aislados (HTTP, SOAP) pueden alojarse en un host aislado.|  
|adaptador de recepción aislado|Adaptador de recepción alojado en un proceso diferente al de BizTalk Server. Este adaptador lo crea y controla el proceso externo, y se registra con BizTalk Server en tiempo de ejecución para enviar mensajes.|  
  
## <a name="k"></a>K  
  
|Término|Definición|  
|----------|----------------|  
|Indicador clave de rendimiento (KPI)|Medidas empresariales que se pueden personalizar que proporciona Analysis Services. Los KPI son atributos relevantes y cálculos asociados que generan pruebas comparativas y objetivos basados en la normativa del sector. Un colección de KPI incluye una medida, un objetivo, propiedades mostradas y variaciones. Las empresas usan los KPI para llevar a cabo un seguimiento del rendimiento y mejorar la capacidad de toma de decisiones.|  
  
## <a name="l"></a>L  
  
|Término|Definición|  
|----------|----------------|  
|puerto enlazado en tiempo de ejecución|Puerto definido en la orquestación que tiene la propiedad Enlace configurada como Especificar más tarde. Un puerto enlazado en tiempo de ejecución se configura cuando se enlaza a un puerto físico. El enlace se realiza utilizando la consola de administración de BizTalk.|  
|aplicación para línea empresarial|Aplicación crucial en la dirección de las empresas, como nóminas, planeamiento de recursos, administración de cadenas de suministros y contabilidad.|  
|datos activos|Datos procesados en ese momento por BizTalk Server.|  
|identificador local único (LUID)|Nombre de un artefacto que lo identifica exclusivamente en el grupo de BizTalk. Los elementos que componen el LUID pueden variar según el tipo de artefacto. Por ejemplo, el LUID para un ensamblado de BizTalk incluye su nombre, su versión, su referencia cultural y su token de clave pública, como Microsoft.BizTalk.Hws.HwsPromotedProperties Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35.|  
|transacción de larga ejecución|Colección de acciones tratadas como unidad, normalmente utilizada para mantener un estado apropiado de una forma predecible y eficaz. La transacción puede producirse en un período indefinido de tiempo y contener varias transacciones anidadas.|  
|registro de bucle|Estructura que puede tener más de una coincidencia en un mensaje de instancia.|  
  
## <a name="m"></a>M  
  
|Término|Definición|  
|----------|----------------|  
|base de datos de administración|Base de datos de Microsoft SQL Server que almacena la información de configuración de los recursos de una organización. Hay una base de datos de administración (a las que en ocasiones se hace referencia como la base de datos de configuración) por organización.|  
|mapa|Archivo XML que define la correspondencia entre los registros y campos de una especificación y los de otra. Una asignación contiene una hoja de estilo del lenguaje de hojas de estilo extensible (XSL) que utiliza BizTalk Server para ejecutar la transformación descrita en la asignación.|  
|cuadrícula del Asignador|Zona media de varias capas de la ventana Asignador de BizTalk, entre los esquemas de origen y destino, en la que se define la asignación de datos.|  
|página de cuadrícula del Asignador|Capa sencilla de la cuadrícula del Asignador que se utiliza para organizar las asignaciones de datos relacionadas de forma independiente de otras asignaciones de datos.|  
|secreto principal|Clave generada por el servidor secreto principal cuando así lo solicita un administrador de inicio de sesión único empresarial (SSO). Esta clave secreta se almacena en el Registro como secreto de Servidor Autoridad de seguridad local (LSA) del servidor secreto principal. Sólo pueden obtener acceso a esta clave secreta los administradores de SSO.|  
|servidor secreto principal|En un entorno distribuido de inicio de sesión único empresarial (SSO), el único equipo que guarda la clave secreta principal del Registro. Puede haber muchos servidores de SSO (en equipos diferentes) que tengan acceso a la base de datos de SSO. Sólo uno de ellos se designa como servidor secreto principal.|  
|message|Instancia electrónica de datos que se intercambian normalmente entre dos aplicaciones o procesos empresariales que se estén ejecutando.|  
|parte del cuerpo de mensaje|Parte principal de un mensaje de BizTalk Server que contiene la carga real y, en casi todos los casos, un Blob de tipo XML. Todos los mensajes deben tener como máximo una parte del cuerpo. Normalmente, los datos leídos desde la transmisión que corresponden a la parte del cuerpo de mensaje de BizTalk Server se utilizan para la promoción de propiedades de mensaje. Por lo tanto, el enrutamiento, publicación o suscripción que se basa en las propiedades promocionadas se lleva a cabo generalmente basándose en la parte del cuerpo.|  
|contexto de mensaje|Contenedor de varias propiedades que utiliza BizTalk Server al procesar el documento.|  
|propiedades de contexto de mensaje|Conjunto de propiedades asociadas con el mensaje.|  
|vista detallada de mensajes|En la página Concentrador de grupo, vista detallada de toda la información conocida para un mensaje determinado en el cuadro de mensajes. Esta vista está disponible en el menú de acceso directo de la lista de campos de tabla dinámica de una de las dos vistas Operaciones.|  
|síntesis del mensaje|Véase otro término: hash|  
|cubo Mensajes|Cubo de procesamiento analítico en línea (OLAP) que agrega información sobre mensajes y servicios. Dos cubos incluidos fuera del cuadro son: mensajes y servicios.|  
|flujo de mensajes|Serie de pasos contiguos de procesamiento a través de los cuales fluyen uno o más mensajes.|  
|vista Flujo de mensajes|Vista de la página Concentrador de grupo que muestra un historial de eventos de procesamiento para mensajes específicos.|  
|encabezado de mensaje|En EDI, parte del mensaje que se utiliza para indicar el inicio de un documento, que es un paquete de segmentos combinados lógicamente que contienen información sobre una transacción. En ANSI X.12, un mensaje equivale a un conjunto de transacciones.|  
|instancia de mensaje|Instancia de un mensaje que está procesando BizTalk Server o ha serializado en el almacén de datos de seguimiento o cuadro de mensajes para seguimiento o procesamiento posterior. Normalmente, en BizTalk Server, se trata de una referencia al mensaje, las propiedades promocionadas del mensaje y del cuerpo de mensaje.|  
|vista Medidas de mensajes|Vista de tabla dinámica de un cubo de procesamiento analítico en línea (OLAP) de medidas de mensaje.|  
|finalizador de mensaje|En EDI, parte del mensaje que se utiliza para indicar el fin de un documento, que es un paquete de segmentos combinados lógicamente que contienen información sobre una transacción. En ANSI X.12, un mensaje equivale a un conjunto de transacciones.|  
|enlace de cuadro de mensajes|Enlace que interactúa con el cuadro de mensajes.|  
|Base de datos de cuadro de mensajes|Grupo de bases de datos de Microsoft SQL Server que contienen información de seguimiento y suscripción de un grupo de cuadro de mensajes.|  
|nodo Cuadro de mensajes|En la consola de administración de BizTalk, nodo utilizado para ver una lista de las bases de datos de cuadro de mensajes que se están utilizando en ese momento.|  
|vista Mensaje|En la página Concentrador de grupo, vista activa de instancias de mensajes usada por los servicios en un cuadro de mensajes. Esta vista está disponible en el menú Operaciones.|  
|Mensajería|Una de las funciones principales de BizTalk Server que implica la recepción, enrutamiento y distribución de mensajes de forma confiable.|  
|Instancia de mensajería|En la página Concentrador de grupo, las instancias de mensajería incluyen instancias de servicio de puerto de envío y puerto de recepción. Las instancias de mensajería hacen referencia a las instancias de servicio de mensajería.|  
|Metadatos|Información como ubicación, hora, tamaño del mensaje o información de excepción.|  
|alias de hito|En BAM, nombre con el que hace referencia a un elemento de datos o hito que contienen las actividades de BAM. Cada elemento de datos e hito puede tener varios alias.|  
|contenido mixto|Contenido de un elemento XML determinado que contiene subelementos y datos no incluidos en estos subelementos. Es un ejemplo de HTML: &lt;P&gt;la luna llena &lt;EM&gt;siempre&lt;/em&gt; sale al anochecer, más o menos.&lt; /P&gt;|  
|tipo de mensaje de varias partes|Definición de la estructura de un mensaje, incluidos los tipos de datos de sus elementos. Un tipo de mensaje de varias partes puede contener varias partes o sólo una.|  
  
## <a name="n"></a>N  
  
|Término|Definición|  
|----------|----------------|  
|nativos|Cualquier formato de datos distinto de XML.|  
|adaptador nativo|Los adaptadores proporcionados por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], que incluyen los adaptadores MQSeries, File, FTP, HTTP, SMTP, SOAP y SQL.|  
|componente de canalización nativa|Componente de canalización que proporciona Microsoft y que viene incluido en BizTalk Server.  Algunos ejemplos son el desensamblador de archivos sin formato, el desensamblador XML y el descodificador de S/MIME.|  
|Nodo|Cada entrada de un árbol de esquema que aparece en el Editor de BizTalk y el Asignador de BizTalk.|  
  
## <a name="o"></a>O  
  
|Término|Definición|  
|----------|----------------|  
|OLAP|Vea Procesamiento analítico en línea.|  
|procesamiento analítico en línea (OLAP)|Tecnología que utiliza estructuras multidimensionales para proporcionar un acceso rápido a los datos para su análisis. Los datos de origen para OLAP están almacenados normalmente en almacenamientos de datos en una base de datos relacional.|  
|operación|Una solicitud o par de solicitud-respuesta de un puerto asociado con una acción de envío o recepción.|  
|vistas de operaciones|En la página Concentrador de grupo, vistas que permiten al usuario ver pero no hacer un seguimiento de los datos activos.|  
|vista detallada de operaciones/mensajes|Vista detallada de toda la información conocida de un mensaje en concreto del cuadro de mensajes.|  
|vista de operaciones/mensajes|Vista activa de mensajes que utilizan los servicios de la base de datos de cuadro de mensajes.|  
|vista detallada de operaciones/servicios|Vista detallada de toda la información conocida de una instancia de servicio en concreto del cuadro de mensajes.|  
|vista de operaciones/servicios|Vista activa de servicios (activos o suspendidos) de la base de datos de cuadro de mensajes; en BizTalk Server 2002, WorkQ/SuspendedQ.|  
|orquestación|Proceso empresarial ejecutable.|  
|enlace de orquestación|Puerto de orquestación que no se conecta con un extremo fijo, sino directamente con el cuadro de mensajes.|  
|Diseñador de orquestaciones|Herramienta de la interfaz de usuario gráfica que se utiliza para diseñar e implementar los procesos empresariales.|  
|instancia de orquestación|Instancia que se está ejecutando de un proceso empresarial ejecutable específico.|  
  
## <a name="p"></a>P  
  
|Término|Definición|  
|----------|----------------|  
|PAM|Véase Administración de acuerdos de socios comerciales (PAM).|  
|parámetro|Hace referencia a los parámetros predeterminados de un proceso empresarial, los parámetros de un proceso empresarial por socio comercial y los parámetros de un proceso empresarial por grupo de socios comerciales.|  
|asociado|Véase también: socio comercial|  
|Administración de acuerdos de socios comerciales (PAM)|Interfaz de usuario del nodo Entidades de la consola de administración de BizTalk Server donde se establecen las propiedades de las entidades. Puede establecer las propiedades de procesamiento para entidades captando el intercambio de documentos de EDI, el proceso por lotes de EDI, el transporte de documentos AS2 y las propiedades globales que se deben usar en ausencia de una entidad.|  
|entidad|Cada entidad externa a BizTalk Server que interactúa con una orquestación. Todos los socios comerciales con los que trata su organización se consideran entidades, y la organización puede tener varios a miles de socios comerciales.|  
|alta de entidades|Mecanismo que une una entidad con una función. Puede dar de alta una entidad en una función, lo que permite a la orquestación interactuar con la entidad.|  
|paso a través|Configuración de los puertos de BizTalk Server en la que un puerto de recepción se conecta directamente a un puerto de envío utilizando únicamente una expresión de filtro de un puerto de envío. La expresión de filtro debería tener la forma BTS.ReceivePortName == "Nombre o puerto de recepción". En esta configuración, cualquier mensaje recibido en el puerto de recepción se enruta directamente con un puerto de envío. El significado de la ejecución paso a través de BizTalk 2004 es distinto de la de la ejecución paso a través de BizTalk Server 2000 ó 2002. En BizTalk Server 2004, el mensaje de ejecución paso a través se sigue procesando en las canalizaciones y se puede transformar en puertos.|  
|supervisión de rendimiento|Proceso de control de la velocidad de recepción o proceso de mensajes, el número de orquestaciones que se están ejecutando, el número de aciertos de caché, el tiempo de utilización de memoria, etc.|  
|reglas de procesamiento de rendimiento|Reglas que controlan el rendimiento de proceso o los contadores de tipo de capacidad.|  
|red perimetral|Colección de dispositivos y subredes que se encuentra entre una red intranet e Internet para ayudar a proteger la red intranet de usuarios de Internet no autorizados. También se conoce como zona desmilitarizada (DMZ) o subred protegida.|  
|enlace físico (anticipado)|Información que lleva el ensamblado y que utiliza el proceso de implementación para crear puertos de envío y recepción.|  
|canalización|Infraestructura de software que define y enlaza una o más fases de procesamiento y las ejecuta en el orden prescrito para completar una tarea específica. Las canalizaciones dividen el procesamiento en fases o abstracciones que describen una categoría de trabajo. También determinan el orden en el que se ejecuta cada categoría de trabajo.|  
|componente de canalización|Componente basado en COM o .NET que puede situarse en una canalización para ejecutar alguna acción de procesamiento en los mensajes que pasen a través de dicha canalización.|  
|Diseñador de canalizaciones|Herramienta gráfica de interfaz de usuario que se utiliza para crear y configurar canalizaciones en BizTalk Server.|  
|directiva|Colección que tiene versión de reglas de negocios.|  
|línea de conexión de puerto|Línea que muestra la conexión entre una forma Envío/Recepción y una operación de una forma Puerto. Ningún extremo de una línea de conexión de puerto puede quedar sin conectar.|  
|tipo de puerto|Propiedad que define el conjunto de patrones de interacción de mensajes denominados "operaciones" que se permiten en un extremo. Una operación podría ser unidireccional, en cuyo caso se envía o recibe un mensaje, o de solicitud-respuesta, en cuyo caso se envía o recibe un mensaje y se envía o recibe una respuesta.|  
|archivo sin formato posicional|Tipo de formato de archivo utilizado para representar los documentos empresariales en los que los registros y campos tienen una longitud fija, con lo que se suprime la necesidad de delimitadores.|  
|cola privada|Cola no publicada como objeto de Active Directory. El Message Queue Server de BizTalk admite completamente el envío y recepción de mensajes en colas privadas.|  
|superficie para el proceso|Área media de la superficie de diseño del Diseñador de orquestaciones. Este área se utiliza para diseñar orquestaciones.|  
|Diseñador de proyectos|Representación visual de los servicios, puertos y enlaces que componen un proyecto. Los usuarios pueden editar los elementos visuales del Diseñador agregando y quitando servicios, y creando y quitando enlaces entre puertos compatibles de los servicios del Diseñador.|  
|promoción de propiedades|El mecanismo a través del cual las propiedades de mensajes específicas se escriben en el contexto del mensaje asociado con el mensaje como campos de propiedades. Propiedades escritas en el contexto del mensaje como campos de propiedades se consideran propiedades promocionadas (la **IsPromoted** propiedad del campo se establece en **True**) y requiere un esquema de propiedad asociada.  Campos de propiedades se utilizan BizTalk Server motor de mensajería para los fines de documentos EDI, seguimiento de los mensajes y evaluación de orquestaciones. El contexto de mensaje para un mensaje se almacena en la columna imgContext de la fila para el mensaje en la tabla de cola de impresión de la base de datos de cuadro de mensajes.|  
|esquema de propiedades|Esquema que asocia a un esquema de BizTalk Server y que se utiliza para identificar los campos de elementos de un documento que se promocionará al contexto de mensaje como campos de propiedades.|  
|configuración de protocolo|Configuración que define la compatibilidad de las transacciones de negocio con un protocolo de negocio a negocio específico Cada perfil de negocio define las distintas configuraciones para el procesamiento de mensajes (codificación) o la transmisión de mensajes (transporte) de cada uno de los protocolos de negocio a negocio mediante los que el socio se puede comunicar. Una configuración de protocolo puede ser para protocolos de codificación o para un protocolo de transporte.|  
|cola pública|Cola que se publica como objeto de Active Directory.|  
|publicación-suscripción|Vea otro término: arquitectura de publicación/suscripción|  
|arquitectura de publicación/suscripción|Combinación de publicación y suscripción que se utiliza para mover mensajes entre subsistemas. Por ejemplo, recibe los mensajes del puerto de recepción, los procesan y los publica en el cuadro de mensajes. BizTalk Server enruta estos mensajes a las orquestaciones de suscripción o puertos de envío que procesan los documentos o los vuelve a publicar en el cuadro de mensajes o los envía a sistemas externos.|  
|publicar|Almacenamiento de una instancia de mensaje en la base de datos de cuadro de mensajes de forma que pueda asociarse con una suscripción de una aplicación que se está utilizando.|  
  
## <a name="q"></a>Q  
  
|Término|Definición|  
|----------|----------------|  
|Expresión de consulta|Grupo de cláusulas de consulta de la página Concentrador de grupo que se puede usar para crear y ejecutar consultas en la base de datos de seguimiento de BizTalk.|  
  
## <a name="r"></a>L  
  
|Término|Definición|  
|----------|----------------|  
|dimensión de intervalo|En BAM, dimensión utilizada para crear gamas de criterios. Por ejemplo, podría crear gamas Baja (0-100), Media (100 - 500), y Alta (500-1000) para describir ventas de unidades numéricas.|  
|generador de recepciones|Componente que genera una recepción falsa para quitar un mensaje de la cola de reintentos.  Este componente se utiliza si se ha configurado un puerto de mensajería para que utilice la mensajería confiable.|  
|controlador de recepción|Instancia de host de BizTalk Server en el que se está ejecutando un adaptador de recepción. Un controlador de recepción es un contenedor lógico de un componente de escucha, un componente del Administrador de extremos y un componente de MessageAgent.|  
|tipo de host de controlador de recepción|Propiedad que restringe el tipo de host que puede alojar un controlador de recepción en concreto.|  
|ubicación de recepción|Noción física de tiempo de diseño de una ubicación (como una URL) y de un tipo de adaptador. Ubicación de recepción del nodo Host de la consola de administración de BizTalk Server que define la funcionalidad de recepción.|  
|canalización de recepción|Canalización que se ejecuta en los mensajes después de que un adaptador los haya recibido y antes de que se publiquen en la base de datos de cuadro de mensajes.|  
|puerto de recepción|Agrupación lógica de ubicaciones de recepción similares.|  
|Volver a implementar|Nueva implementación de un ensamblado que ya existe en el entorno de destino eliminando los bits antiguos e implementando los nuevos.|  
|volver a hidratar|Volver a activar una orquestación inactiva en memoria del almacén permanente como resultado de algún evento, como la recepción de un mensaje.|  
|Vista Relevancia|Vista del asignador de BizTalk por la que elementos del mismo nivel no pertinentes de un esquema se contraen para proporcionar una vista más compacta del esquema. Esto reduce la necesidad de desplazarse y se centra en las partes útiles del esquema y asignación.|  
|vistas de informe|Conjunto jerárquico de vistas que muestran uno o varios procesos empresariales.|  
|repositorio|Contenedor de almacenamiento de los metadatos que utiliza Analysis Services. Los metadatos se almacenan en tablas de una base de datos relacional y se utilizan para definir los parámetros y las propiedades de los objetos del servidor de análisis. Las herramientas XML utilizan el repositorio en modo de lectura y escritura, y el Explorador de BizTalk obtiene acceso a la información en modo de sólo lectura.|  
|adaptador de solicitud-respuesta|Adaptador de recepción que recibe un mensaje de solicitud del cliente, lo envía al servidor, espera una respuesta y, luego, envía la respuesta de vuelta al cliente.|  
|forma Retorno|Forma utilizada para finalizar una orquestación en algún punto antes del verdadero fin de la orquestación.  Un ejemplo de esto podría ser: si (comprobación de seguridad correcta), continúe.|  
|rol|Colección de tipos de puertos que utilizan un servicio o que implementan un servicio, proporcionando los medios por los que las entidades interactúan con las orquestaciones. Por ejemplo, una orquestación puede que utilice la función de un remitente. El remitente tendría una o dos entidades asociadas con él. Cuando la orquestación decide qué compañía remitente se va a utilizar para enviar un elemento, compara los precios de las entidades de la función del remitente.|  
|vínculo de función|Relación entre funciones definida por el mensaje y los tipos de puerto utilizados en las interacciones bidireccionales.|  
|tipo de vínculo de función|Propiedad que caracteriza la relación entre dos servicios u orquestaciones definiendo el papel que desempeña cada servicio en la relación y especificando los tipos de puerto que proporciona cada función.|  
|nodo raíz|Nodo de esquema de BizTalk Server que representa el elemento XML más alejado del documento empresarial especificado por el esquema.|  
|Ventana ATR|Define el período de tiempo al cabo del cual se agregan los datos de una agregación en tiempo real (ATR). Por ejemplo, si el período de tiempo es un día y el punto del tiempo corresponde al momento presente, únicamente verá agregaciones correspondientes a los datos de las últimas 24 horas. Dado que el punto del tiempo cambia continuamente, el período de tiempo de la ventana ATR también cambia. Como consecuencia, también se hace referencia a este elemento como a una ventana de tiempo en movimiento.|  
|regla|Par de condiciones y acciones.|  
|conjunto de reglas|Agrupación lógica de reglas similares. Se puede ver como mecanismo de agrupación o partición del motor de reglas.|  
|marco de trabajo del motor de reglas|Biblioteca de componentes .NET, API y servicios que utilizan los programadores de aplicaciones para escribir aplicaciones basadas en reglas.|  
|servicio de actualización del motor de reglas|Servicio que ejecuta actualizaciones dinámicas de directivas.|  
|Almacén de reglas|Ubicación de las directivas guardadas. El almacén de reglas predeterminado es la base de datos de SQL.|  
  
## <a name="s"></a>S  
  
|Término|Definición|  
|----------|----------------|  
|esquema|Estructura de un mensaje. Un esquema puede contener varios subesquemas.|  
|extensión del editor de esquemas|Mecanismo mediante el cual los módulos de software amplían la funcionalidad básica XML/XSD que admite el Editor de BizTalk. Las Extensiones de editor de esquemas agregan normalmente propiedades suplementarias a uno o más nodos de los esquemas de BizTalk para representar sus semánticas concretas.|  
|subred filtrada|Vea otro término: red de perímetro|  
|Capa de sockets seguros|Protocolo que mejora la seguridad de la comunicación de datos mediante una combinación de cifrado de datos, certificados digitales y criptografía de clave pública. SSL habilita la autenticación y aumenta la integridad de los datos y la privacidad a través de las redes. SSL no proporciona autorización o no rechazo.|  
|segmento|En EDI, combinación lógica de elementos. Por ejemplo, en un segmento se combinan los detalles de dirección y nombre.|  
|etiqueta de segmento|En EDI, único identificador de un segmento. Dentro de EDIFACT, por ejemplo, las etiquetas de segmento son códigos de tres letras mayúsculas anteriores a los elementos incluidos en un documento. En ANSI X.12, las etiquetas de segmento son códigos de dos o tres letras mayúsculas. Una etiqueta de segmento es similar a un identificador de tipo de registro.|  
|controlador de envío|Host de BizTalk Server con el que se asocia el adaptador de envío.|  
|canalización de envío|Canalización que se ejecuta en los mensajes antes de que se envíen al servidor BizTalk Server.|  
|puerto de envío|Ubicación a la que se envían los mensajes o desde la cual se reciben, y tecnología que se utiliza para implementar la acción de comunicación. La ubicación sólo se identifica por el nombre del puerto.|  
|grupo de puertos de envío|Agrupación lógica de puertos de envío. Cuando un mensaje se envía a un grupo de puertos de envío, se dirige a todos los puertos de envío asociados. También recibe el nombre de lista de distribución.|  
|del ssDE|Programa, rutina o proceso que ejecuta una función de sistema específica para admitir otros programas en el nivel de sistemas operativos, como el servicio de Windows NT. Se trata de servicios de Windows NT o COM+ que se ejecutan en un servidor.|  
|instancia de servicio|Generalmente se refiere a una instancia de una orquestación que BizTalk Server está procesando o ha serializado en el cuadro de mensajes para mayor procesamiento o seguimiento. Normalmente se trata de una representación serializada del estado de la orquestación y hace referencia a cualquier mensaje que se use en la orquestación. En el contexto de mensajería, una instancia de servicio se aplica una instancia de un puerto, por ejemplo, un puerto de recepción donde la entrada es la ubicación de recepción y la salida se publica en la base de datos de recuadro de mensajes, o un puerto de envío donde la entrada es el cuadro de mensajes y la salida es normalmente un adaptador de envío.|  
|vista Medidas de servicio|Vista de tabla dinámica del cubo OLAP de medidas de servicio. Anteriormente formaba parte de la vista Agregación.|  
|sesión|Conexión lógica creada entre dos hosts para intercambiar datos. Normalmente, las sesiones utilizan secuencias y confirmaciones para enviar datos.|  
|forma|Representación gráfica de una acción o agrupación de acciones de una orquestación.|  
|conector de formas|Línea utilizada para enlazar formas y determinar su orden relativo en una orquestación.|  
|forma Simple|Forma de una orquestación que no puede contraerse y no puede contener otras formas.|  
|Inicio de sesión único|Vea otro término: Enterprise Single Sign-On system|  
|administración de inicio de sesión único (SSO)|Modelo de objetos al que se puede obtener acceso mediante las utilidades administrativas de línea de comandos (como comandos ssomanage y ssoconfig) y mediante el instrumental de administración de Windows (WMI) y el Explorador de BizTalk de los escenarios de almacén de configuración. Este componente establece la comunicación con la base de datos de SSO mediante el servidor de SSO.|  
|grupo Administradores de inicio de sesión único (SSO)|Administrador que detecta el nivel más alto de autoridad y que normalmente configura la clave de cifrado.|  
|grupo Administradores de aplicación afiliada de inicio de sesión único (SSO)|Administradores que pueden crear y administrar aplicaciones afiliadas, especificar la cuenta de administradores de aplicación de inicio de sesión única (SSO) para cada aplicación afiliada y llevar a cabo todas las tareas de administración que puedan realizar los administradores y los usuarios de aplicación de inicio de sesión único (SSO).|  
|grupo Administradores de aplicación de inicio de sesión único (SSO)|Administradores que se asignan específicamente a cada aplicación afiliada.|  
|utilidades de cliente de inicio de sesión único (SSO)|Utilidades disponibles como parte de la característica Administración destinadas a usuarios finales para proporcionar las asignaciones de credenciales en la base de datos de SSO. El servidor de SSO las utiliza para establecer comunicación con la base de datos de SSO.|  
|Base de datos de Inicio de sesión único (SSO)|Base de datos en la que se almacenan las credenciales del inicio de sesión único empresarial (SSO). Otras bases de datos almacenan los puertos de envío y URL; sólo una tiene el subservicio secreto.|  
|servidor de inicio de sesión único (SSO)|Servidor en el que se instala el servicio de inicio de sesión único empresarial (SSO).|  
|servicios de inicio de sesión único (SSO)|Servicios que habilitan el inicio de sesión único para adaptadores mediante el acceso a credenciales en la base de datos de SSO. Estos servicios sirven para administrar la base de datos de SSO. Al igual que el almacén de configuración, estos servicios sirven para tener acceso a los datos de configuración de los adaptadores.|  
|Etiqueta inteligente|Advertencia gráfica que indica que una forma no está configurada completamente y que sugiere ideas sobre cómo proceder.|  
|Adaptador de SMTP|Adaptador que implementa el protocolo SMTP (es decir, que envía mensajes de correo electrónico) para interactuar con aplicaciones para negocios. Este adaptador sólo incluye el controlador de envío.|  
|Adaptador de SOAP|Adaptador que implementa el protocolo SOAP para interactuar con aplicaciones para negocios, publica orquestaciones como servicios Web y consume servicios Web externos.|  
|error de SOAP|Mensaje de error que devuelve el servicio Web que transmite una excepción de aplicación del servicio Web.|  
|Encabezado SOAP|Elemento opcional incluido en el sobre de un mensaje SOAP que puede contener datos que no estén directamente relacionados con la funcionalidad principal del método de servicio Web XML.|  
|mensaje SOAP|documento XML con formato correcto. Debería utilizar el sobre SOAP y el espacio de nombres de codificación SOAP e incluir una declaración opcional XML, con un sobre SOAP (elemento raíz) compuesto de un encabezado opcional SOAP y un cuerpo de mensaje SOAP.|  
|seguimiento de mensajes SOAP|Método para establecer un punto de interrupción en un servicio Web publicado para devolver excepciones detalladas a un cliente Web.|  
|adaptador petición-respuesta|Adaptador de envío bidireccional. Un adaptador de envío de petición-respuesta envía un mensaje de solicitud desde BizTalk Server al destino, espera al mensaje de respuesta y lo vuelve a enviar a BizTalk Server.|  
|esquema de origen|Esquema utilizado en una asignación de BizTalk Server que representa la estructura de los mensajes de instancia de salida.|  
|Adaptador de SQL|Adaptador que intercambia información entre BizTalk Server y una base de datos del servidor SQL Server.|  
|SSO|Vea Sistema de inicio de sesión único empresarial (SSO).|  
|fase|Parte de una canalización dedicada a finalizar una categoría determinada de trabajo. Los componentes de canalización de una fase finalizan las tareas.|  
|base de datos provisional|Base de datos utilizada por una herramienta de comprobación para implementar el ensamblado con sus enlaces en la prueba o base de datos provisional.|  
|adaptador estático|Adaptador que utiliza la interfaz de usuario disponible en el marco de trabajo de adaptadores.|  
|puerto estático|Puerto de envío que tiene una dirección de destino y un tipo de adaptador asociado con él. En oposición al puerto de envío dinámico, un puerto de envío estático no puede cambiar la configuración en tiempo de ejecución y siempre se utiliza para enviar mensajes a una única dirección de destino.|  
|archivo de clave de nombre seguro|Archivo que contiene la identidad de un ensamblado (su nombre de texto simple, número de versión e información de referencia cultural, si se proporciona) más una clave pública y una firma digital. Se genera de un archivo de ensamblado mediante la clave privada correspondiente. (El archivo de ensamblado contiene el manifiesto del ensamblado, que contiene los nombres y valores hash de todos los archivos que forman el ensamblado.)|  
|enviar|Colocación de un mensaje y de sus propiedades asociadas en las tablas correspondientes de la base de datos de cuadro de mensajes y exploración de las suscripciones del directorio Suscripción cuyos predicados coinciden con las propiedades del mensaje.|  
|subscribe|Mecanismo de BizTalk para indicar al cuadro de mensajes que enrute mensajes con propiedades que coincidan con parámetros específicos (suscripciones) a los procesos adecuados. Por ejemplo, los filtros del puerto de envío crean suscripciones en el cuadro de mensajes. Cuando se publican mensajes en el cuadro de mensajes que coinciden con la especificación de filtros, BizTalk Server enruta los mensajes al puerto de envío de suscripción para que los procese.|  
|suscripción|Mecanismo para enrutar mensajes que coincidan con algunos criterios de la comparación de propiedades en una cola de trabajo.|  
|Base de datos de suscripciones|Base de datos de cuadro de mensajes que contiene todas las suscripciones de un grupo de cuadro de mensajes.|  
|instancia suspendida|Instancia de un mensaje u orquestación que BizTalk Server ha dejado de procesar debido a un error que se ha producido en el sistema o en el mensaje. Las instancias suspendidas por errores en el sistema generalmente se pueden reanudar cuando se haya solucionado el error en el sistema. Normalmente, las instancias suspendidas por problemas de mensajes no se pueden reanudar y el mensaje se debe fijar y volver a enviar al sistema de BizTalk Server.|  
|cola de suspensión|Cola que contiene elementos de trabajo para los que se ha detectado un error durante el procesamiento. Una cola suspendida almacena los mensajes hasta que se puedan corregir, volver a procesar o eliminar.|  
  
## <a name="t"></a>T  
  
|Término|Definición|  
|----------|----------------|  
|entorno o base de datos de destino|Se identifican al implementar un ensamblado y sus enlaces en un entorno de destino.|  
|tarea|Aspecto humano en una acción. Cada acción puede tener cero o más tareas que se asignan cada una a distintos destinos. Existe una correspondencia de uno a uno entre tareas y destinos.|  
|respuesta de tarea|Respuestas a la tarea desde los destinos. Cada tarea puede tener cero o más respuestas.|  
|TDDS|Consulte Servicio de descodificación de datos de seguimiento.|  
|vista Detalles técnicos|Vista de la página Concentrador de grupo que muestra los pasos técnicos de procesamiento de un único subproceso de actividad.|  
|Término|Entidad atómica con un valor que se puede utilizar en predicados y acciones. Puede ser un miembro de clase (método, propiedad de clase .NET o campo, elemento XML, elemento de bases de datos), una variable de reglas o una constante.|  
|dimensión de tiempo|Elemento de interfaz de usuario que describe el tiempo como se utiliza en agregaciones.|  
|mensaje de temporización|Mensaje de temporización insertado en la cola de mensajes que desencadena el retroceso de la transmisión hacia la cola.|  
|cuadro de herramientas|Ventana acoplable que contiene una serie de elementos que se pueden utilizar en el proceso de diseño de orquestaciones.|  
|información sobre herramientas|Pequeña ventana emergente que proporciona una breve ayuda contextual cuando se mueve el puntero del mouse sobre el elemento.|  
|TPE|Vea Editor de perfiles de seguimiento.|  
|Seguimiento|Capacidad para efectuar un seguimiento de los intercambios y mensajes procesados por BizTalk Server.|  
|base de datos de análisis de seguimiento|Nombre de la base de datos de análisis de seguimiento (OLAP) del grupo de cuadro de mensajes asociado.|  
|Servicio de descodificación de datos de seguimiento (TDDS)|Servicio que mueve los datos de eventos desde la base de datos de cuadro de mensajes a la base de datos de importación principal de BAM. Este servicio procesa y almacena tanto la inteligencia empresarial como los datos de supervisión de estado de BizTalk.|  
|Base de datos de seguimiento|Base de datos del servidor SQL Server que almacena la información de seguimiento de un grupo de cuadro de mensajes. Existe una base de datos de seguimiento por grupo de cuadro de mensajes.|  
|vista Opciones de seguimiento|Vista de la página Concentrador de grupo que define las opciones de seguimiento.|  
|perfil de seguimiento|Conjunto de características que definen un proceso relacionado con los negocios y que contienen la asignación entre una orquestación específica y una definición de actividad  Un perfil de seguimiento es un archivo con extensión .btt.|  
|Editor de perfiles de seguimiento|Herramienta gráfica de interfaz de usuario que sirve para definir las partes interesantes del proceso empresarial y los datos interesantes de la carga empresarial.|  
|socio comercial|Organización externa o interna con la que su organización intercambia datos electrónicos. Por ejemplo, un socio comercial podría ser un proveedor, un cliente o un departamento interno.|  
|acuerdo de socio comercial|Acuerdo definitivo y vinculante entre dos socios comerciales para transacciones de mensajes mediante un protocolo específico de negocio a negocio. Un acuerdo de socio comercial combina propiedades comunes de mensajes bidireccionales de perfiles de negocio específicos de ambos socios. Es una recopilación completa de todos los aspectos que rigen una transacción empresarial entre dos socios comerciales. El acuerdo de socio comercial se deriva normalmente de los perfiles de cada socio, con capacidad de personalizar e invalidar la configuración necesaria.|  
|administración de socio comercial|Acción de administrar y almacenar información sobre socios, sus negocios y los acuerdos y relaciones de negocio a negocio. La solución de administración de socios comerciales (TPM) mejorada refleja con más intuición las entidades y relaciones del negocio, permitiendo así a las organizaciones administrar mejor las asociaciones de negocio con socios comerciales.|  
|entidad comercial|Entidad que se encuentra en el nivel de raíz de una solución de administración de socios comerciales (TPM). Cada organización partícipe en una relación de negocio en curso y cualquier entidad de negocio individual que ejecute BizTalk Server y envíe mensajes a otra entidad o los reciba de ella, es una entidad comercial.|  
|mensajería transaccional|Transmisión de mensajes enviados en orden exactamente una vez, que se consigue mediante la sincronización y la coordinación de varias instancias de adaptadores de Message Queue Server de BizTalk en un grupo.|  
|Forma Transformación|Forma de una orquestación que se utiliza para mover datos de un mensaje a otro y lo transforma mediante el uso de una asignación XSLT.|  
|transformación|Proceso de conversión de un documento XML que se adapta a un esquema en un documento XML que se adapta a otro esquema y que frecuentemente cambia la estructura del documento en el proceso.|  
|traducción|Proceso de conversión de un documento XML a un formato nativo (diferente de XML) o viceversa.|  
|acuerdo de transporte|Acuerdo entre los perfiles de negocio de dos socios comerciales para usar un protocolo de transporte específico (AS2) al intercambiar mensajes.|  
|Seguridad de la capa de transporte|Protocolo que proporciona privacidad y seguridad a las comunicaciones entre dos aplicaciones que se comunican a través de una red. TLS cifra las comunicaciones y permite a los clientes autenticar servidores y, opcionalmente, a los servidores autenticar clientes. TLS es una versión más segura del protocolo Secure Sockets Layer (SSL).|  
|protocolo de transporte|Protocolo que rige el canal de transporte usado para enviar mensajes entre dos socios. Con respecto a la administración de socios comerciales (TPM), únicamente se admite el protocolo AS2.|  
  
## <a name="u"></a>U  
  
|Término|Definición|  
|----------|----------------|  
|anular la implementación |Proceso de eliminación de una aplicación de BizTalk de las bases de datos de BizTalk Server y de la consola de administración de BizTalk, así como quitar la aplicación de cualquier equipo en el que estuviera instalada.|  
|dar de baja|Acto de eliminación de todas las suscripciones e instancias (en ejecución o suspendidas) de este servicio.|  
|Directorio de Elementos de Datos Comerciales de las Naciones Unidas (UNTDED)|En EDI, directorio de todos los elementos utilizados en la norma EDIFACT.|  
|UNTDED|Vea Directorio de Elementos de Datos Comerciales de las Naciones Unidas.|  
|Segmento UNZ|En EDI, segmento de finalizador de intercambio de un documento EDIFACT. Incluye los elementos de referencia de intercambio y el número de documentos del intercambio. El segmento se utiliza para indicar el final de un intercambio, y para comprobar la referencia y el número de documentos del intercambio.|  
  
## <a name="v"></a>V  
  
|Término|Definición|  
|----------|----------------|  
|Control de versiones|Actualización de la implementación de un artefacto y del aumento de su número de versión.|  
|nodo virtual|En el esquema, nodo que no corresponde directamente a un atributo o elemento XML de los mensajes de instancia definidos por el esquema.|  
|vocabulario|Colección de elementos de vocabulario utilizados en la composición de reglas.|  
|elemento de vocabulario|Nombre legible de un hecho.|  
  
## <a name="w"></a>W  
  
|Término|Definición|  
|----------|----------------|  
|Servicios web|Una unidad de lógica de la aplicación que proporcionan datos y servicios a otras aplicaciones. Las aplicaciones obtienen acceso a los servicios Web XML mediante protocolos Web y formatos de datos estándar como HTTP, XML y SOAP, independientemente del modo en que se implementan los servicios Web XML. Los servicios Web XML combinan los mejores aspectos de Internet y del desarrollo basado en los componentes, y son los pilares del modelo de programación Microsoft .NET.|  
|Lenguaje de descripción de servicios Web (WSDL)|Lenguaje con formato XML que describe servicios Web como extremos para el intercambio de mensajes. Presenta la característica de extensibilidad para permitir la descripción de extremos y sus mensajes independientemente del formato de éstos y del protocolo de red. Se trata del lenguaje que usa UDDI (Universal Description, Discovery, and Integration), un directorio empresarial basado en la Web.|  
|Instrumental de administración de Windows (WMI)|Componente del sistema operativo de Microsoft Windows y de la implementación de Microsoft de la Administración empresarial basada en Web (WBEM), utilizado para automatizar las tareas administrativas en un entorno empresarial.|  
|WMI|Consulte “Instrumental de administración de Windows (WMI)”|  
|cola de trabajo|Cola que contiene los mensajes que se van a procesar por un servidor de BizTalk.|  
|WSDL|Vea Lenguaje de descripción de servicios Web (WSDL).|  
  
## <a name="x"></a>X  
  
|Término|Definición|  
|----------|----------------|  
|certificado X.509|Formato de certificados estándar que utilizan los procesos de Windows basados en certificados. Un certificado X.509 contiene la clave pública e información acerca de la persona o entidad para la que se emite el certificado, información acerca del certificado e información opcional acerca de la entidad emisora (CA) del mismo.|  
|XDR|Vea Datos reducidos XML (XDR).|  
|Lenguaje de definición de esquemas XML (XSD)|Lenguaje de esquemas. Un esquema XML define los elementos, atributos y tipos de datos que se adaptan a la parte 1 del esquema XML de World Wide Web Consortium (W3C): Recomendación de estructuras del lenguaje de definición de esquemas XML. El W3C XML Schema Part 2: Datatypes Recommendation es la recomendación para definir los tipos de datos utilizados en los esquemas XML. El lenguaje de definición de esquemas XML permite definir la estructura y los tipos de datos de los mensajes XML.|  
|datos reducidos XML (XDR)|Una de las varias formas de las que se puede describir la estructura de un documento XML.  BizTalk Server puede abrir un esquema descrito mediante un archivo XDR, pero lo convierte a lenguaje de definición de esquemas XML (XSD) en el proceso.|  
|XPath|Lenguaje exhaustivo utilizado para desplazarse por la jerarquía de un documento XML. Las expresiones XPath contienen información de atributos y elementos XML, seleccionan los datos que cumplen unos criterios específicos y llevan a cabo una comparación de los datos recuperados. También se denomina "ruta del nodo".|  
|XSD|Vea Lenguaje de definición de esquemas XML (XSD).|  
|XSLT|Consulte “Transformación de lenguaje de hojas de estilo extensible (XSLT)”.|  
  
## <a name="z"></a>Z  
  
|Término|Definición|  
|----------|----------------|  
|zombi|Mensaje que no se ha procesado mediante ninguna orquestación. No se encuentra en la cola Suspendido ni en ninguna otra parte donde se reintente.|  
|restablecedor de zombie|Orquestación que escucha en la base de datos de cuadro de mensajes o zombies y resucita los que cumplen con determinados criterios.|