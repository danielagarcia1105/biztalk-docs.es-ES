---
title: 'Tutorial 2: Los proyectos de migración de BizTalk de Siebel | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2a1828-8cc8-4b80-99bd-c083c04e5d04
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b8d138d348e750102d82a4aba2e39bc7d119c8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223012"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a>Tutorial 2: Migración de proyectos de BizTalk de Siebel
La versión anterior del adaptador de Siebel que se incluye con Microsoft BizTalk Server difiere basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en muchos aspectos, como:  
  
-   La experiencia en tiempo de diseño de creación de un proyecto de BizTalk.  
  
-   La experiencia de recuperación de metadatos.  
  
-   Nombre de archivo de esquema y espacio de nombres.  
  
-   Asignaciones de tipos de datos.  
  
-   Las operaciones que pueden realizarse usando el adaptador.  
  
-   Configuración del puerto físico en la consola de administración de BizTalk Server  
  
 Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante la versión anterior del adaptador de Siebel](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).  
  
 Sin embargo, puede realizar cambios en el proyecto de BizTalk creado con la versión anterior del adaptador y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
 Este tutorial proporciona instrucciones sobre los cambios que se debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.  
  
> [!NOTE]
>  En este tutorial, por brevedad, la versión anterior del adaptador de Siebel se conocerán como adaptador de Siebel vPrev. De forma similar, un proyecto de BizTalk que usa el adaptador de Siebel vPrev se conocerán como proyecto de BizTalk vPrev.  
  
## <a name="sample-used-for-the-tutorial"></a>Ejemplo usado para el Tutorial  
 Este tutorial se basa en un ejemplo (Siebel_BussComp_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que realiza una operación de inserción en el componente de negocio de Siebel de cuenta. El ejemplo se proporciona con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplo del adaptador](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial consiste en un proyecto de BizTalk que realiza una operación de inserción en el componente de negocio de la cuenta.  
  
-   Debe tener un mensaje de solicitud para realizar una operación de inserción en el componente de negocio de cuenta mediante el adaptador de Siebel vPrev. El mensaje de solicitud debe ajustarse al esquema de la operación de inserción generado con el adaptador de Siebel vPrev.  
  
-   Debe haber completado los pasos descritos en [requisitos previos para crear aplicaciones Siebel](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md).  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev creado son:  
  
-   **Orquestación de BizTalk**. Se trata de una orquestación sencilla que toma los mensajes de solicitud desde una ubicación de archivo, envía el mensaje de solicitud al sistema Siebel usando un Siebel envío y recepción puerto, recibe la respuesta y lo guarda en otra ubicación del archivo.  
  
-   **Esquema para la operación que se va a realizar en el componente de negocio de Siebel**. Este tutorial consiste en un proyecto de BizTalk que realiza una operación de inserción en el componente de negocio de la cuenta. El esquema generado para el componente de negocio de la cuenta es AccountService_Account_x5d.xsd. Este esquema se genera mediante el adaptador de Siebel vPrev.  
  
    > [!NOTE]
    >  A diferencia de basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], el adaptador de Siebel vPrev no admite la generación de metadatos para operaciones específicas en un componente empresarial. De forma predeterminada, el adaptador genera esquemas para todas las operaciones compatibles en el componente empresarial. Para más tales diferencias entre el adaptador de Siebel vPrev y basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [migrar BizTalk proyectos creado mediante la versión anterior del adaptador de Siebel](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).  
  
-   **Mensaje de solicitud**. El mensaje de solicitud para realizar una operación de inserción en el componente de negocio de la cuenta. El esquema del mensaje de solicitud se ajusta al esquema de la operación de inserción como obtenidas por el adaptador de Siebel vPrev.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite enviar un mensaje de solicitud, que se ajusta al esquema generado por el adaptador de Siebel vPrev, utilizando un puerto personalizado de WCF que sólo puede procesar mensajes sean conformes a las basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Por lo tanto, en resumen, el ejercicio de migración implica configurar el puerto personalizado de WCF para procesar los mensajes que no cumplen basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]del esquema.  
  
 Sin embargo, para poder configurar correctamente el puerto de WCF-Custom, debe realizar las siguientes tareas:  
  
-   Generar metadatos para la operación de inserción en el componente de negocio de cuenta mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
-   Asignar el mensaje de solicitud para realizar una operación de inserción con el adaptador de Siebel vPrev a un mensaje de solicitud para realizar una operación de inserción mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] al mensaje de respuesta para el adaptador de Siebel vPrev.  
  
-   Crear un Siebel de WCF-Custom envío y recepción de puerto en la consola de administración de BizTalk Server.  
  
-   Configurar el puerto de WCF-Custom para utilizar las asignaciones de solicitud y respuesta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Modificar el proyecto de BizTalk en la base de datos de Oracle vPrev](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server para usar el adaptador de la base de datos de ORacle](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [Paso 3: Probar la aplicación migran con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)