---
title: 'Tutorial 2: Migración de un proyecto de BizTalk RFC de SAP | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf741fdbbf996fa54c227cc879c850304413d25f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978989"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a>Tutorial 2: Migración de un proyecto de BizTalk RFC de SAP
La versión anterior del adaptador SAP que se incluye con Microsoft BizTalk Server difiere basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en muchos aspectos, como:  
  
- La experiencia en tiempo de diseño de la creación de un proyecto de BizTalk.  
  
- La experiencia de recuperación de metadatos.  
  
- Nombre de archivo de esquema y espacio de nombres.  
  
- Asignaciones de tipos de datos.  
  
- Las operaciones que pueden realizarse mediante el adaptador.  
  
- Configuración de puerto físico en la consola de administración de BizTalk Server.  
  
  Estas diferencias se explican en los temas de [migrar BizTalk proyectos creado mediante la versión anterior del adaptador SAP](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).  
  
  Sin embargo, puede realizar cambios en el proyecto de BizTalk creado con la versión anterior del adaptador y que funcione con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
  Este tutorial proporciona instrucciones sobre los cambios que debe realizar en el proyecto de BizTalk existente creado con la versión anterior del adaptador.  
  
> [!NOTE]
>  En este tutorial, por brevedad, la versión anterior del adaptador de SAP se hará referencia a como adaptador SAP vPrev. De forma similar, se hará referencia a un proyecto de BizTalk que usa el adaptador SAP vPrev como proyecto de BizTalk vPrev.  
  
## <a name="sample-used-for-the-tutorial"></a>Ejemplo usado para el Tutorial  
 En este tutorial se basa en un ejemplo (SAP_RFC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que invoca una solicitud de cambio en un sistema SAP. El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial trata de un proyecto de BizTalk que invoca la RFC SD_RFC_CUSTOMER_GET.  
  
-   Debe tener un mensaje de solicitud para invocar la RFC SD_RFC_CUSTOMER_GET mediante el adaptador SAP vPrev. El mensaje de solicitud debe ajustarse al esquema de RFC generado mediante el adaptador de SAP vPrev. El ejemplo proporcionado para este tutorial contiene este mensaje de solicitud.  
  
-   [Crear el archivo de clave de nombre seguro y obtener información sobre las herramientas](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creado con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev para invocar una RFC son:  
  
-   **Orquestación de BizTalk**. Se trata de una orquestación sencilla que selecciona los mensajes de solicitud desde una ubicación de archivo, envía el mensaje de solicitud al sistema SAP mediante SAP envío y recepción de puerto, recibe la respuesta y lo guarda en otra ubicación del archivo.  
  
-   **Esquema para la solicitud de cambio que desea invocar en el sistema SAP**. Este tutorial trata de un proyecto de BizTalk que invoca la RFC SD_RFC_CUSTOMER_GET. El esquema generado para la solicitud de cambio es SD_RFC_CUSTOMER_GET__x32003.xsd. Este esquema se genera mediante el adaptador de SAP vPrev.  
  
-   **Mensaje de solicitud**. El mensaje de solicitud para invocar la RFC SD_RFC_CUSTOMER_GET. El esquema del mensaje de solicitud se ajusta al esquema de RFC SD_RFC_CUSTOMER_GET como obtenidas por el adaptador SAP vPrev.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creado con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite enviar un mensaje de solicitud, que se ajusta al esquema generado por el adaptador SAP vPrev, mediante un puerto personalizado de WCF que sólo puede procesar los mensajes que cumplen el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Por lo tanto, en resumen, el ejercicio de migración implica configurar el puerto de WCF-Custom para procesar los mensajes que no se ajustan a la basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]del esquema.  
  
 Sin embargo, para poder configurar correctamente el puerto de WCF-Custom, debe realizar las siguientes tareas:  
  
- Generar metadatos para RFC SD_RFC_CUSTOMER_GET mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- Asignar el mensaje de solicitud para invocar la solicitud de cambio con un adaptador SAP vPrev para un mensaje de solicitud para invocar la solicitud de cambio con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- Asignar el mensaje de respuesta recibido con el basado en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] al mensaje de respuesta para el adaptador SAP vPrev.  
  
- Creación de un SAP de WCF-Custom envío y recepción de puerto en la consola de administración de BizTalk Server.  
  
- Configure el puerto de WCF-Custom para usar las asignaciones de solicitud y respuesta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Modificar el proyecto vPrev de BizTalk para invocar una RFC](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [Paso 2: Configurar la orquestación en la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [Paso 3: Probar la aplicación migrada](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador de SAP](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)