---
title: 'Tutorial 2: Migrar un proyecto de BizTalk RFC de SAP | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80b5d53904b96267b1877310aa3480ce34a1bedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a>Tutorial 2: Migrar un proyecto de BizTalk RFC de SAP
La versión anterior del adaptador SAP que se incluye con Microsoft BizTalk Server difiere basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en muchos aspectos, como:  
  
-   La experiencia en tiempo de diseño de creación de un proyecto de BizTalk.  
  
-   La experiencia de recuperación de metadatos.  
  
-   Nombre de archivo de esquema y espacio de nombres.  
  
-   Asignaciones de tipos de datos.  
  
-   Las operaciones que pueden realizarse usando el adaptador.  
  
-   Configuración del puerto físico en la consola de administración de BizTalk Server.  
  
 Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante la versión anterior del adaptador SAP](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).  
  
 Sin embargo, puede realizar cambios en el proyecto de BizTalk creado con la versión anterior del adaptador y ponerla en marcha con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
 Este tutorial proporciona instrucciones sobre los cambios que se debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.  
  
> [!NOTE]
>  En este tutorial, por brevedad, la versión anterior del adaptador SAP se conocerán como adaptador SAP vPrev. De forma similar, un proyecto de BizTalk que usa el adaptador SAP vPrev se conocerán como proyecto de BizTalk vPrev.  
  
## <a name="sample-used-for-the-tutorial"></a>Ejemplo usado para el Tutorial  
 Este tutorial se basa en un ejemplo (SAP_RFC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que invoca una solicitud de cambio en un sistema SAP. El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial consiste en un proyecto de BizTalk que invoca la RFC SD_RFC_CUSTOMER_GET.  
  
-   Debe tener un mensaje de solicitud para llevar a cabo para invocar la solicitud de cambio de SD_RFC_CUSTOMER_GET con un adaptador SAP vPrev. El mensaje de solicitud debe ajustarse al esquema de la solicitud de cambio que se genera mediante el adaptador SAP vPrev. El ejemplo que se proporciona para este tutorial contiene el siguiente mensaje de solicitud.  
  
-   [Crear archivo de clave de nombre seguro y obtenga información acerca de las herramientas](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev para invocar una solicitud de cambio son:  
  
-   **Orquestación de BizTalk**. Se trata de una orquestación sencilla que toma los mensajes de solicitud desde una ubicación de archivo, envía el mensaje de solicitud al sistema SAP mediante SAP envío y recepción puerto, recibe la respuesta y lo guarda en otra ubicación del archivo.  
  
-   **Esquema para la solicitud de cambio que desea invocar en el sistema SAP**. Este tutorial consiste en un proyecto de BizTalk que invoca la RFC SD_RFC_CUSTOMER_GET. El esquema generado para la solicitud de cambio es SD_RFC_CUSTOMER_GET__x32003.xsd. Este esquema se genera con un adaptador SAP vPrev.  
  
-   **Mensaje de solicitud**. El mensaje de solicitud para invocar la solicitud de cambio de SD_RFC_CUSTOMER_GET. El esquema del mensaje de solicitud se ajusta al esquema de la solicitud de cambio de SD_RFC_CUSTOMER_GET como obtenidas por el adaptador SAP vPrev.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite enviar un mensaje de solicitud, que se ajusta al esquema generado por el adaptador SAP vPrev, utilizando un puerto personalizado de WCF que sólo puede procesar mensajes sean conformes a las basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Por lo tanto, en resumen, el ejercicio de migración implica configurar el puerto personalizado de WCF para procesar los mensajes que no cumplen basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]del esquema.  
  
 Sin embargo, para poder configurar correctamente el puerto de WCF-Custom, debe realizar las siguientes tareas:  
  
-   Generar metadatos para la solicitud de cambio de SD_RFC_CUSTOMER_GET mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Asignar el mensaje de solicitud para invocar la solicitud de cambio con un adaptador SAP vPrev a un mensaje de solicitud para invocar la solicitud de cambio con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] al mensaje de respuesta para el adaptador SAP vPrev.  
  
-   Crear un SAP de WCF-Custom envío y recepción de puerto en la consola de administración de BizTalk Server.  
  
-   Configurar el puerto de WCF-Custom para utilizar las asignaciones de solicitud y respuesta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Modificar el proyecto de BizTalk vPrev para llamar a una solicitud de cambio](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [Paso 3: Probar la aplicación migrada](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador SAP](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)