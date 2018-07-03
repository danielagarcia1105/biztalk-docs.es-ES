---
title: 'Tutorial 2: Los proyectos de migración de BizTalk de Siebel | Microsoft Docs'
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
ms.openlocfilehash: 3ada19454c3d2aef1c725987d8d37f7b98a2d1c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996437"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a>Tutorial 2: Migración de proyectos de BizTalk de Siebel
La versión anterior del adaptador de Siebel al que se incluye con Microsoft BizTalk Server difiere basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en muchos aspectos, como:  
  
- La experiencia en tiempo de diseño de la creación de un proyecto de BizTalk.  
  
- La experiencia de recuperación de metadatos.  
  
- Nombre de archivo de esquema y espacio de nombres.  
  
- Asignaciones de tipos de datos.  
  
- Las operaciones que pueden realizarse mediante el adaptador.  
  
- Configuración de puerto físico en la consola de administración de BizTalk Server  
  
  Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante la versión anterior del adaptador de Siebel](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).  
  
  Sin embargo, puede realizar cambios en el proyecto de BizTalk creado con la versión anterior del adaptador y que funcione con el basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
  Este tutorial proporciona instrucciones sobre los cambios que debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.  
  
> [!NOTE]
>  En este tutorial, por brevedad, la versión anterior del adaptador de Siebel se hará referencia a como adaptador de Siebel vPrev. De forma similar, se hará referencia a un proyecto de BizTalk que usa el adaptador de Siebel vPrev como proyecto de BizTalk vPrev.  
  
## <a name="sample-used-for-the-tutorial"></a>Ejemplo usado para el Tutorial  
 En este tutorial se basa en un ejemplo (Siebel_BussComp_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que realiza una operación de inserción en el componente empresarial de Siebel de cuenta. El ejemplo se proporciona con Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplo de adaptador](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial trata de un proyecto de BizTalk que realiza una operación de inserción en el componente de negocio de la cuenta.  
  
-   Debe tener un mensaje de solicitud para realizar una operación de inserción en el componente de negocio de la cuenta mediante el adaptador de Siebel vPrev. El mensaje de solicitud debe ajustarse al esquema de la operación de inserción generado mediante el adaptador de Siebel vPrev.  
  
-   Debe haber completado los pasos descritos en [requisitos previos para crear aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md).  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creado con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev creado son:  
  
- **Orquestación de BizTalk**. Se trata de una orquestación sencilla que selecciona los mensajes de solicitud desde una ubicación de archivo, envía el mensaje de solicitud al sistema Siebel mediante un Siebel envío y recepción de puerto, recibe la respuesta y lo guarda en otra ubicación del archivo.  
  
- **Esquema para la operación que desea realizar en el componente empresarial de Siebel**. Este tutorial trata de un proyecto de BizTalk que realiza una operación de inserción en el componente de negocio de la cuenta. El esquema generado para el componente de negocio de la cuenta es AccountService_Account_x5d.xsd. Este esquema se genera mediante el adaptador de Siebel vPrev.  
  
  > [!NOTE]
  >  A diferencia de basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], el adaptador de Siebel vPrev no admite la generación de metadatos para operaciones específicas en un componente empresarial. De forma predeterminada, el adaptador genera esquemas para todas las operaciones admitidas en el componente empresarial. Para más de esas diferencias entre el adaptador de Siebel vPrev y basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [migrar BizTalk proyectos creado mediante la versión anterior del adaptador de Siebel](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).  
  
- **Mensaje de solicitud**. El mensaje de solicitud para realizar una operación de inserción en el componente de negocio de la cuenta. El esquema del mensaje de solicitud se ajusta al esquema de la operación de inserción como obtenidas por el adaptador de Siebel vPrev.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creado con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite enviar un mensaje de solicitud, que se ajusta al esquema generado por el adaptador de Siebel vPrev, mediante un puerto personalizado de WCF que sólo puede procesar los mensajes que cumplen el basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Por lo tanto, en resumen, el ejercicio de migración implica configurar el puerto de WCF-Custom para procesar los mensajes que no se ajustan a la basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]del esquema.  
  
 Sin embargo, para poder configurar correctamente el puerto de WCF-Custom, debe realizar las siguientes tareas:  
  
- Generar metadatos para la operación de inserción en el componente empresarial de cuenta con el basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
- Asignar el mensaje de solicitud para realizar una operación de inserción mediante el adaptador de Siebel vPrev para un mensaje de solicitud para realizar una operación de inserción mediante basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
- Asignar el mensaje de respuesta recibido con el basado en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] al mensaje de respuesta para el adaptador de Siebel vPrev.  
  
- Crear un Siebel de WCF-Custom envío y recepción de puerto en la consola de administración de BizTalk Server.  
  
- Configure el puerto de WCF-Custom para usar las asignaciones de solicitud y respuesta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Modificar el proyecto vPrev de BizTalk en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server para usar el adaptador de base de datos de ORacle](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [Paso 3: Probar la aplicación migrado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)