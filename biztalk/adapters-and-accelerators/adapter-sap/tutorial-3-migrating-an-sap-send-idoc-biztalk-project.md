---
title: 'Tutorial 3: Migrar una SAP enviar IDOC proyecto de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52f8bc638d1adefe952ce055542706d11e0ca61f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217044"
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a>Tutorial 3: Migrar un proyecto de BizTalk SAP IDOC de envío
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
 Este tutorial se basa en un ejemplo (SendIDOC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que envía un IDOC a un sistema SAP. El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial consiste en un proyecto de BizTalk que envía un IDOC BOMDOC a un sistema SAP.  
  
-   Debe tener un archivo sin formato BOMDOC IDOC para enviar al sistema SAP mediante el adaptador SAP vPrev. El ejemplo que se proporciona para este tutorial contiene este IDOC de archivo sin formato.  
  
-   [Crear archivo de clave de nombre seguro y obtenga información acerca de las herramientas](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev para enviar un IDOC son:  
  
-   **Orquestación de BizTalk**. Se trata de una orquestación sencilla que toma un IDOC de archivo sin formato desde una ubicación de archivo y envía el IDOC al sistema SAP mediante SAP puerto de envío. El proyecto de BizTalk contiene un desensamblador de archivos sin formato para convertir el IDOC de archivo sin formato en un XML, por lo que se puede utilizar en una orquestación. Antes de que el puerto de envío de SAP de vPrev consume el IDOC XML, se convierte en un IDOC de archivo sin formato mediante un ensamblador de archivo sin formato.  
  
-   **Esquema para el IDOC que desee enviar al sistema SAP**. Para este tutorial, tiene un proyecto de BizTalk que envía BOMDOC01 IDOC al sistema SAP. El esquema generado para el IDOC es BOMDOC01.xsd. Este esquema se genera con un adaptador SAP vPrev.  
  
-   **El IDOC de archivo sin formato**. Se trata de la que se envía al sistema SAP IDOC de archivo sin formato.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite enviar un IDOC de archivo sin formato a un sistema SAP mediante un puerto de envío WCF-Custom en lugar del puerto de envío para el adaptador SAP vPrev. Antes de comprender qué configuración es necesaria para el puerto de envío WCF-Custom, primero debe entender qué puertos físicos son necesarios para la orquestación de IDOC vPrev envío:  
  
-   Un archivo de puerto de recepción que recoge el IDOC de archivo sin formato. Este puerto utiliza la canalización de desensamblador de archivos sin formato, disponible en la aplicación de BizTalk, para convertir el archivo sin formato en un XML que se ajusta al esquema (BOMDOC01.xsd) generado con el adaptador SAP vPrev.  
  
-   Un SAP vPrev puerto de envío que envía el IDOC de archivo sin formato al sistema SAP. Antes de enviar el archivo sin formato, el puerto utiliza el ensamblador de archivo sin formato para convertir el XML IDOC en un IDOC de archivo sin formato.  
  
 Para migrar el proyecto de BizTalk vPrev existente, no es necesario cambiar el archivo de puerto de recepción que recoge el IDOC de archivo sin formato y convierte el IDOC de archivo sin formato a XML mediante un desensamblador de archivo sin formato. Solo debe configurar un puerto de envío WCF-Custom con la configuración de la configuración correcta. Este tutorial muestra cómo configurar el puerto de envío WCF-Custom para enviar los IDOC a un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para enviar un IDOC](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [Paso 2: Configurar un puerto de envío unidireccional de WCF-Custom](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [Paso 3: Probar la aplicación migrada](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador SAP](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)