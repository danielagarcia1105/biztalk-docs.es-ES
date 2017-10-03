---
title: 'Tutorial: Migrar proyectos de BizTalk para el adaptador de la base de datos de Oracle | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a393219-bae8-4e08-acc8-76986600d0de
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0948e79b7f236bb20bbff9101195809bcc921a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a>Tutorial: Migrar proyectos de BizTalk para el adaptador de la base de datos de Oracle
El adaptador de BizTalk ODBC para Oracle base de datos que se incluye con Microsoft BizTalk Server difiere basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en muchos aspectos, como:  
  
-   La experiencia en tiempo de diseño de creación de un proyecto de BizTalk.  
  
-   La experiencia de recuperación de metadatos.  
  
-   Nombre de archivo de esquema y espacio de nombres.  
  
-   Asignaciones de tipos de datos.  
  
-   Las operaciones que pueden realizarse usando el adaptador.  
  
-   Configuración del puerto físico en la consola de administración de BizTalk Server  
  
 Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante el adaptador de BizTalk ODBC para la base de datos de Oracle](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).  
  
 Sin embargo, puede realizar cambios en el proyecto de BizTalk que se creó mediante el adaptador de BizTalk ODBC para la base de datos de Oracle y ponerla en marcha con basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 Este tutorial proporciona instrucciones sobre los cambios que se debe realizar en el proyecto de BizTalk existente creado con el adaptador de BizTalk ODBC para la base de datos de Oracle.  
  
> [!NOTE]
>  En este tutorial, por brevedad, el adaptador de BizTalk ODBC para la base de datos de Oracle se conocerán como "adaptador de base de datos de Oracle vPrev." De forma similar, un proyecto de BizTalk que usa el adaptador de la base de datos de Oracle vPrev se conocerán como "proyecto de BizTalk vPrev".  
  
## <a name="sample-used-for-the-tutorial"></a>Ejemplo usado para el Tutorial  
 Este tutorial se basa en un ejemplo (Oracle_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev. El ejemplo se proporciona con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial consiste en un proyecto de BizTalk que realiza una operación de inserción en una tabla de clientes. La tabla CUSTOMER se crea en el esquema SCOTT mediante la ejecución de los scripts SQL que se proporcionan con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos.  
  
-   Debe tener un mensaje de solicitud para realizar una operación de inserción en la base de datos de Oracle mediante el adaptador de la base de datos de Oracle vPrev. El mensaje de solicitud debe ajustarse al esquema de la operación de inserción generado con el adaptador de la base de datos de Oracle vPrev.  
  
-   Debe haber completado los pasos descritos en [requisitos previos](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md) 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev creado son:  
  
-   **Orquestación de BizTalk**. Se trata de una orquestación sencilla que toma los mensajes de solicitud desde una ubicación de archivo, envía el mensaje de solicitud a la base de datos de Oracle mediante Oracle envío y recepción puerto, recibe la respuesta y lo guarda en otra ubicación del archivo.  
  
-   **Esquema para la operación que se va a realizar en la base de datos de Oracle**. Este tutorial consiste en un proyecto de BizTalk que realiza una operación de inserción en la tabla de clientes en el esquema SCOTT. La tabla CUSTOMER se crea en el esquema SCOTT mediante la ejecución de los scripts SQL que se proporcionan con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos. El esquema generado para la tabla CUSTOMER es CUSTOMERService_CUSTOMER_x5d.xsd. Este esquema se genera mediante el adaptador de la base de datos de Oracle vPrev.  
  
    > [!NOTE]
    >  A diferencia de basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], el adaptador de la base de datos de Oracle vPrev no admite la generación de metadatos para las operaciones concretas en una tabla de base de datos de Oracle. De forma predeterminada, el adaptador genera esquemas para todas las operaciones que se puede usar en la tabla. Para más tales diferencias entre el adaptador de la base de datos de Oracle vPrev y basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [migrar BizTalk proyectos creado mediante el adaptador de BizTalk ODBC para la base de datos de Oracle](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).  
  
-   **Mensaje de solicitud**. El mensaje de solicitud para realizar una operación de inserción en la tabla CUSTOMER. El esquema del mensaje de solicitud se ajusta al esquema de la operación de inserción como obtenidas por la versión anterior del adaptador de base de datos de Oracle.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite enviar un mensaje de solicitud, que se ajusta al esquema generado por el adaptador de base de datos de Oracle vPrev, utilizando un puerto personalizado de WCF que sólo puede procesar mensajes sean conformes a las basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Por lo tanto, en resumen, el ejercicio de migración implica configurar el puerto personalizado de WCF para procesar los mensajes que no cumplen basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]del esquema.  
  
 Sin embargo, para poder configurar correctamente el puerto de WCF-Custom, debe realizar las siguientes tareas:  
  
-   Generar metadatos para la operación de inserción en el SCOTT. Tabla CUSTOMER usando basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
-   Asignar el mensaje de solicitud para realizar una operación de inserción con el adaptador de la base de datos de Oracle vPrev a un mensaje de solicitud para realizar una operación de inserción mediante basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] al mensaje de respuesta para el adaptador de la base de datos de Oracle vPrev.  
  
-   Crear un Oracle WCF-Custom envío y recepción de puerto en la consola de administración de BizTalk Server.  
  
-   Configurar el puerto de WCF-Custom para utilizar las asignaciones de solicitud y respuesta.  
  
 
  
## <a name="see-also"></a>Vea también  
[Introducción a Biztalk Server](../../core/getting-started-with-biztalk-server.md)