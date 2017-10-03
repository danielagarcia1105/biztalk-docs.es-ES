---
title: 'Tutorial 4: Migrar una SAP recibir IDOC proyecto de BizTalk | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943c80e84bc192330fd870a45c0b5fb60761a33d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a>Tutorial 4: Migrar una SAP recibir IDOC proyecto de BizTalk
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
 Este tutorial se basa en un ejemplo (ReceiveIDOC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que recibe un IDOC de archivo sin formato de un sistema SAP. El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial consiste en un proyecto de BizTalk que recibe un IDOC ORDERS03 desde un sistema SAP.  
  
-   [Crear archivo de clave de nombre seguro y obtenga información acerca de las herramientas](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creados con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev para recibir un IDOC son:  
  
-   **Orquestación de BizTalk**. Se trata de una sencilla orquestación que consta de una SAP puerto de recepción que recibe un IDOC de archivo sin formato de un sistema SAP. El proyecto de BizTalk contiene un desensamblador de archivos sin formato para convertir el IDOC de archivo sin formato en un XML, por lo que se puede utilizar en una orquestación. Antes de que el XML IDOC se copia en una ubicación de archivo a través de un puerto de archivo, se convierte en un IDOC de archivo sin formato mediante un ensamblador de archivo sin formato.  
  
-   **Esquema para el IDOC que desee enviar al sistema SAP**. Este tutorial consiste en un proyecto de BizTalk que recibe los IDOC ORDERS03 desde el sistema SAP. El esquema generado para el IDOC es ORDERS03.xsd. Este esquema se genera con un adaptador SAP vPrev.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creados con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es que le permite recibir un IDOC de archivo sin formato de un sistema SAP mediante un puerto de envío WCF-Custom en lugar del puerto de envío para el adaptador SAP vPrev. Antes de comprender qué configuración es necesaria para el puerto de envío WCF-Custom, primero debe entender qué puertos físicos son necesarios para la orquestación de IDOC vPrev envío.  
  
-   Un SAP vPrev puerto de recepción que recibe un IDOC de archivo sin formato de un sistema SAP. El puerto también lo convierte en un IDOC XML mediante un desensamblador de archivos sin formato, que está disponible como parte de la aplicación de BizTalk vPrev. El XML IDOC cumple el esquema (ORDERS03.xsd) que se han generado mediante el adaptador SAP vPrev.  
  
-   Un puerto de envío de archivo que copia el IDOC en la carpeta. Este puerto también usa la canalización de ensamblador de archivo sin formato, disponible en la aplicación de BizTalk, para convertir el XML IDOC en un IDOC de archivo sin formato.  
  
 Para migrar el proyecto de BizTalk vPrev existente, no es necesario cambiar el puerto de envío de archivo que se copia el IDOC de archivo sin formato en una carpeta. Solo debe configurar un nuevo puerto con la configuración de la configuración correcta de recepción WCF-Custom. Este tutorial muestra cómo configurar el WCF-Custom puerto de recepción para recibir IDOC desde un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para recibir un IDOC](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [Paso 2: Configurar un unidireccionales de WCF-Custom puerto de recepción](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [Paso 3: Probar la aplicación migrada](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador SAP](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)