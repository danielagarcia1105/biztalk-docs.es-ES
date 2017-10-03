---
title: 'Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ca17095841fb154be9ec34766a34f174414cd82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a>Tutorial 1: Migrar proyectos de BizTalk para el adaptador de SQL
La versión anterior del adaptador de SQL que se incluye con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] difiere basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en muchos aspectos, como:  
  
-   La experiencia en tiempo de diseño de creación de un proyecto de BizTalk.  
  
-   La experiencia de recuperación de metadatos.  
  
-   Nombre de archivo de esquema y espacio de nombres.  
  
-   Asignaciones de tipos de datos.  
  
-   Las operaciones que pueden realizarse usando el adaptador.  
  
-   Configuración del puerto físico en la consola de administración de BizTalk Server  
  
 Estas diferencias se explican en los temas de migración de BizTalk proyectos creado mediante la versión anterior de la creación.  
  
 Sin embargo, puede realizar cambios en el proyecto de BizTalk que se creó con la versión anterior del adaptador y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 Este tutorial proporciona instrucciones sobre los cambios que se debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.  
  
> [!NOTE]
>  En este tutorial, por brevedad, la versión anterior del adaptador SQL se conocerán como adaptador de SQL vPrev. De forma similar, un proyecto de BizTalk que usa el adaptador de SQL vPrev se conocerán como proyecto de BizTalk vPrev.  
  
> [!IMPORTANT]
>  Este tutorial proporciona instrucciones sobre cómo migrar un proyecto de BizTalk de adaptador SQL vPrev que realiza una operación de inserción básico en una tabla de base de datos de SQL Server. Este tutorial no trata todos los posibles escenarios para la migración desde el adaptador de SQL vPrev al nuevo basado en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Debe utilizar este tutorial de migración como base y modifique según corresponda para realizar cambios que son pertinentes para el proyecto existente.  
  
## <a name="sample-used-for-the-tutorial"></a>Ejemplo usado para el Tutorial  
 Este tutorial se basa en un ejemplo (SQL_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev. El ejemplo se proporciona con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, vea los ejemplos.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial consiste en un proyecto de BizTalk que realiza una operación de inserción en una tabla de clientes en la base de datos de SQL Server. La tabla de clientes tiene el siguiente diseño:  
  
    |Nombre de la columna|Description|  
    |-----------------|-----------------|  
    |v_custid|Tipo de entero clave, principal, el campo de identidad|  
    |Nombre|tipo de nchar(10)|  
  
-   Debe tener un mensaje de solicitud para realizar una operación de inserción en la base de datos de SQL Server mediante el adaptador SQL vPrev. El mensaje de solicitud debe ajustarse al esquema de la operación de inserción generado con el adaptador de SQL vPrev.  
  
-   Debe haber completado los pasos descritos en [antes de que desarrollar aplicaciones de BizTalk](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev creado son:  
  
-   **Orquestación de BizTalk**. Se trata de una orquestación sencilla que toma los mensajes de solicitud desde una ubicación de archivo, envía el mensaje de solicitud a la base de datos de SQL Server mediante un WCF-Custom envío y recepción puerto, recibe la respuesta y lo guarda en otra ubicación del archivo.  
  
-   **Esquema para la operación que se va a realizar en la base de datos de SQL Server**. Este tutorial consiste en un proyecto de BizTalk que realiza una operación de inserción en la tabla Customer. El esquema generado para la tabla Customer es InsertCustomerService.xsd. Este esquema se genera mediante el adaptador de SQL vPrev.  
  
-   **Mensaje de solicitud**. El mensaje de solicitud para realizar una operación de inserción en la tabla Customer. El esquema del mensaje de solicitud se ajusta al esquema de la operación de inserción como obtenidas por la versión anterior del adaptador de SQL.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite enviar un mensaje de solicitud, que se ajusta al esquema generado por el adaptador de SQL vPrev, mediante un puerto personalizado de WCF que sólo puede procesar mensajes sean conformes a las basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Por lo tanto, en resumen, el ejercicio de migración implica configurar el puerto personalizado de WCF para procesar los mensajes que no cumplen basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]del esquema.  
  
 Sin embargo, para poder configurar correctamente el puerto de WCF-Custom, debe realizar las siguientes tareas:  
  
-   Generar metadatos para la operación de inserción en la tabla Customer usando basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
-   Asignar el mensaje de solicitud para realizar una operación de inserción con el adaptador de SQL vPrev a un mensaje de solicitud para realizar una operación de inserción mediante basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] al mensaje de respuesta para el adaptador SQL vPrev.  
  
-   Crear una instancia de SQL de WCF-Custom envío y recepción de puerto en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
-   Configurar el puerto de WCF-Custom para utilizar las asignaciones de solicitud y respuesta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Modificar el proyecto de BizTalk mediante el adaptador de SQL vPrev](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [Paso 3: Probar la aplicación migrados que utiliza el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)