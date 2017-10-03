---
title: "Mediante la consola de administración de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], how to
- Administration Console [BizTalk Server], about Administration Console
- artifacts, list
- groups, Hub
ms.assetid: af00d9de-0f94-407b-b6f4-4da63a0867a0
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 079bae61dd4e692e25634414f6ff2e7078235b67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-biztalk-server-administration-console"></a>Utilizar la consola de administración de BizTalk Server
La consola de administración de BizTalk Server es un caso de Microsoft Management Console (MMC) que puede utilizar para administrar y supervisar BizTalk Server, y que puede usar para implementar y administrar las aplicaciones de BizTalk Server.  
  
 La parte izquierda de la consola de administración de BizTalk Server, el árbol de consola, consta de carpetas y subcarpetas que representan distintos tipos de artefactos que puede administrar.  
  
 Cuando selecciona un nodo del árbol de consola, el panel de detalles situado en la parte derecha de la consola de administración muestra información sobre los elementos.  
  
 Si selecciona el nodo de administración de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] en el árbol de consola, se muestra la página de inicio, que contiene acciones que puede llevar a cabo, tal como conectarse a un grupo existente de BizTalk Server. Asimismo, la página de inicio además incluye vínculos a la documentación de BizTalk Server y a sitios web de comunidades en línea.  
  
 Para obtener información sobre cómo usar métodos abreviados de teclado para la consola de administración, consulte [métodos abreviados de teclado de consola de administración](../core/administration-console-keyboard-shortcuts.md).  
  
## <a name="biztalk-server-artifacts"></a>Artefactos de BizTalk Server  
 Puede administrar los artefactos siguientes mediante la consola de administración de BizTalk Server:  
  
-   **Grupo de BizTalk**. El nodo de grupo de BizTalk del árbol de consola contiene nodos adicionales que representan los artefactos (configuración de plataforma, aplicaciones y entidades) para el grupo de BizTalk. Los grupos de BizTalk son unidades de organización que suelen representar empresas, departamentos, concentradores u otras unidades de negocio que requieren una implementación contenida de BizTalk Server. Un grupo de BizTalk tiene una relación de uno a uno con una base de datos de administración de BizTalk. Para obtener más información, consulte [administrar grupos](../core/managing-groups.md).  
  
     Cuando se selecciona el nodo de grupo de BizTalk en la consola de administración de BizTalk Server, se muestra la página concentrador de grupo de BizTalk Server en el panel de detalles. La página Concentrador de grupo de BizTalk Server proporciona una vista general del estado del sistema de BizTalk Server. Para obtener más información, consulte [mediante la página concentrador de grupo](../core/using-the-group-hub-page.md).  
  
-   **Orquestación**. Una orquestación se diseña mediante el Diseñador de orquestaciones y se implementa en el grupo de BizTalk bajo el que aparece en la consola de administración. Para obtener más información, consulte [administrar orquestaciones](../core/managing-orchestrations.md).  
  
-   **Vínculos de función**. Un vínculo de función define la relación entre funciones mediante la definición de los tipos de mensaje y de puerto que se empleen en las interacciones en ambas direcciones. Para obtener más información, consulte [administrar vínculos de función](../core/managing-role-links.md).  
  
-   **Grupos de puertos de envío**. Un grupo de puertos de envío es una colección de puertos de envío que se puede utilizar para enviar el mismo mensaje a varios destinos con una única configuración. Para obtener más información, consulte [administrar puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md).  
  
-   **Puertos de envío**. Un puerto de envío es un objeto de BizTalk que envía mensajes. Para obtener más información, consulte [administrar puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md).  
  
-   **Puertos de recepción**. Un puerto de recepción es una agrupación lógica de ubicaciones de recepción similares. Para obtener más información, consulte [administrar puertos de recepción](../core/managing-receive-ports.md).  
  
-   **Ubicaciones de recepción**. Una ubicación de recepción se define como una dirección específica a la que llegan documentos entrantes y una canalización de BizTalk Server que procesa el mensaje recibido en la dirección. Para obtener más información, consulte [administrar ubicaciones de recepción](../core/managing-receive-locations.md).  
  
-   **Directivas**. Las directivas son colecciones de reglas de negocios y tienen asignada una versión. Para obtener más información, consulte [administrar directivas](../core/managing-policies.md).  
  
-   **Esquemas**. Un esquema es una estructura de un mensaje. Un esquema puede contener varios subesquemas. Para obtener más información, consulte [administrar esquemas](../core/managing-schemas.md).  
  
-   **Mapas de**. Una asignación es un archivo XML que define la correspondencia entre los registros y campos en una especificación y los registros y los campos en otra. Una asignación contiene una hoja de estilo del lenguaje de hojas de estilo extensible (XSL) que utiliza BizTalk Server para ejecutar la transformación descrita en la asignación. Para obtener más información, consulte [administrar mapas](../core/managing-maps.md).  
  
-   **Las canalizaciones**. Una canalización es una infraestructura de software que define y vincula una o más fases de procesamiento, las ejecuta en un orden prescrito para completar una tarea específica. Las canalizaciones dividen el procesamiento en fases o abstracciones que describen una categoría de trabajo. También determinan el orden en el que se ejecuta cada categoría de trabajo. Para obtener más información, consulte [administrar canalizaciones](../core/managing-pipelines.md).  
  
-   **Recursos**. Un recurso es una secuencia de comandos, un ensamblado implementado u otro archivo asociado con una aplicación. Para obtener más información, consulte [administrar recursos](../core/managing-resources.md).  
  
-   **Entidades**. Una entidad es una entidad externa a BizTalk Server que interactúa con una orquestación. Todos los socios comerciales con los que trata su organización se consideran entidades, y la organización puede tener varios miles de socios comerciales. Para obtener más información, consulte [administrar entidades](../core/managing-parties.md).  
  
-   **Configuración de plataforma**. El nodo Configuración de plataforma contiene subnodos para hosts, instancias de host, bases de datos de cuadros de mensaje y adaptadores. Para obtener más información, consulte [administrar la configuración de plataforma](../core/managing-platform-settings.md).  
  
    -   **Hosts**. El nodo Hosts contiene todos los hosts aislados y de tipo En curso del entorno de BizTalk Server. Un host de BizTalk es un contenedor lógico para elementos como controladores de adaptadores, ubicaciones de recepción (incluidas las canalizaciones) y orquestaciones. Para obtener más información, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).  
  
    -   **Instancias de host**. El nodo Instancias de host contiene todas las instancias de host del grupo actual de BizTalk Server. Las instancias de host son procesos en tiempo de ejecución de BizTalk Server que ejecutan los componentes de aplicación.  
  
         Si utiliza el nodo Instancias de host, se puede crear una instancia de host nueva y actualizar la información de la instancia de host. Para obtener más información, consulte [administración de Hosts de BizTalk e instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md).  
  
    -   **Servidores**. El nodo Servidores enumera todos los servidores que se han unido al grupo de BizTalk Server. Éstos son los equipos en los que BizTalk Server se encuentra instalado y configurado, y donde se ejecutan las instancias de host. Las instancias de host se crean mediante la asociación del servidor con un host determinado. Para obtener más información, consulte [administrar servidores](../core/managing-servers.md).  
  
    -   **Cuadros de mensaje**. El nodo Cuadros de mensaje contiene todas las bases de datos de cuadros de mensajes que utiliza el grupo actual de BizTalkServer. Puede crear una base de datos nueva de cuadros de mensaje y actualizar la información de la base de datos de cuadros de mensaje mediante el nodo Cuadros de mensaje. La base de datos de cuadros de mensaje es la base para el equilibrio de la carga de elemento de trabajo entre servidores que realizan un procesamiento conjunto. Un elemento de trabajo se puede pasar a través de una base de datos de cuadros de mensaje más de una vez durante su vida de procesamiento. El nombre de la base de datos de cuadros de mensaje no puede superar los 100 caracteres. Para obtener más información, consulte [administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md).  
  
    -   **Adaptadores**. El nodo Adaptadores contiene los subnodos de todos los adaptadores de envío y recepción que están configurados para el grupo de BizTalk Server y los controladores de adaptadores asociados. Los adaptadores constituyen el software de mensajería intermedio utilizado para enviar y recibir mensajes entre extremos. Para obtener más información, consulte [usando adaptadores](../core/using-adapters.md).  

## <a name="tips-and-tricks"></a>Sugerencias y trucos

#### <a name="update-settings-for-multiple-hosts-and-host-instances-simultaneously"></a>Actualizar la configuración de varios hosts e instancias de host simultáneamente
A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede seleccionar varios hosts e instancias de host y actualizar algunos de los valores de **panel de configuración**.

**Pasos**:

1. En administración de BizTalk, expanda **grupo de BizTalk**y expanda **configuración de plataforma**.
2. Seleccione **Hosts**. En la lista de hosts, use las teclas CTRL o MAYÚS para seleccionar varios hosts al mismo tiempo.
3. Haga clic en los hosts que seleccionó y seleccione **configuración**. O bien, seleccione **configuración** en el panel Acciones.
4. En el panel de configuración general y configuración de la limitación pueden establecer y aplicar a varios hosts que ha seleccionado. 
5. A continuación, seleccione **instancias de Host**. En la lista de instancias de host, utilice las teclas CTRL o MAYÚS para seleccionar varias instancias de host al mismo tiempo. En **configuración**, .NET CLR y configuración de la limitación de orquestación pueden aplicarse a las distintas instancias de host que seleccionó. 

> [!NOTE]
> Puede seleccionar varios host e instancias de host que son del mismo tipo de Host. Si el tipo de host es diferente, el **configuración** opción aparece atenuada. Por ejemplo, si se hospedan en un proceso de selección múltiple y un host aislado, a continuación, **configuración** aparece en gris.

#### <a name="filter-artifacts-in-your-application"></a>Filtrar los artefactos de la aplicación
A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], también puede buscar artefactos en la aplicación. Por ejemplo, puede buscar un esquema específico o una orquestación en una aplicación. 

**Pasos**:

1. En administración de BizTalk, expanda **grupo de BizTalk**, expanda **aplicaciones**y expanda una de las aplicaciones que tiene los artefactos. Por ejemplo, expanda la **aplicación EDI de BizTalk**. 
2. Seleccione **esquemas**. En la lista de esquemas, utilice la **búsqueda** cuadro para buscar un esquema o filtrar los esquemas que se muestran. Por ejemplo, escriba en **x12** en el cuadro de búsqueda y presione ENTRAR. Se muestran todos los esquemas con X12 en el nombre. Borrar la búsqueda. 

    A continuación, escriba en **lote** en el cuadro de búsqueda y presione ENTRAR. El se muestran los esquemas por lotes. 
    
Puede utilizar esta búsqueda para buscar o filtrar los artefactos con la aplicación, incluidos los puertos de envío, recursos, asignaciones y así sucesivamente. 

#### <a name="save-multiple-suspended-messages-simultaneously-to-a-file-within-group-hub"></a>Guardar varios mensajes suspendidos simultáneamente en un archivo dentro del concentrador de grupo 
A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede guardar varios mensajes suspendidos simultáneamente en un archivo.

**Pasos**:

1. En administración de BizTalk, seleccione **grupo de BizTalk**
2. Seleccione **nueva consulta**y en la consulta, **Buscar para**

    Nombre del campo: Busque  
    Operador: es igual a  
    Valor: mensajes
3. Seleccione **Ejecutar consulta**. En los resultados de consulta, utilice las teclas CTRL o MAYÚS para seleccionar varias instancias suspendidas al mismo tiempo. Haga clic en y seleccione **seguro al archivo**. 
4. Elija la carpeta para guardar los archivos. Al guardar, se crea un archivo XML para cada mensaje.

## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo abrir la consola de administración de BizTalk Server](../core/how-to-open-the-biztalk-server-administration-console.md)  
  
-   [Configurar el seguimiento mediante la consola de administración de BizTalk Server](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)  
  
-   [Mediante la página concentrador de grupo](../core/using-the-group-hub-page.md)