---
title: 'Tutorial 4: Migración de una SAP recibir IDOC proyecto de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e943c3663767d2b684b0f4657f639d752705b86f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011261"
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a>Tutorial 4: Migración de una SAP recibir IDOC proyecto de BizTalk
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
 En este tutorial se basa en un ejemplo (ReceiveIDOC_Migration) que muestra cómo migrar un proyecto de BizTalk vPrev que recibe un IDOC de archivo sin formato de un sistema SAP. El ejemplo se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener un proyecto de BizTalk vPrev. Este tutorial trata de un proyecto de BizTalk que recibe un IDOC ORDERS03 desde un sistema SAP.  
  
-   [Crear el archivo de clave de nombre seguro y obtener información sobre las herramientas](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Descripción de un proyecto de BizTalk creado con la versión anterior del adaptador  
 Los componentes claves de un proyecto de BizTalk vPrev para recibir un IDOC son:  
  
-   **Orquestación de BizTalk**. Se trata de una sencilla orquestación que consta de una SAP puerto de recepción que recibe un IDOC de archivo sin formato de un sistema SAP. El proyecto de BizTalk contiene un desensamblador de archivo sin formato para convertir el IDOC de archivo sin formato a XML, por lo que se puede usar en una orquestación. Antes de que el IDOC XML se copia en una ubicación de archivo a través de un puerto de archivos, se convierte en un IDOC de archivo sin formato mediante un ensamblador de archivo sin formato.  
  
-   **Esquema para el IDOC que desee enviar al sistema SAP**. Este tutorial trata de un proyecto de BizTalk que recibe los IDOC ORDERS03 desde el sistema SAP. El esquema generado para el IDOC es ORDERS03.xsd. Este esquema se genera mediante el adaptador de SAP vPrev.  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>Cómo migrar un proyecto de BizTalk creado con la versión anterior del adaptador  
 El objetivo de este tutorial de migración es para que pueda recibir un IDOC de archivo sin formato de un sistema SAP mediante un puerto de envío WCF-Custom en lugar del puerto de envío para el adaptador SAP vPrev. Antes de comprender qué configuración es necesaria para el puerto de envío WCF-Custom, debe comprender primero qué puertos físicos son necesarios para la orquestación de IDOC de envío vPrev.  
  
- Un vPrev SAP puerto de recepción que recibe un IDOC de archivo sin formato de un sistema SAP. El puerto también lo convierte en un IDOC XML con un desensamblador de archivo sin formato, que está disponible como parte de la aplicación de BizTalk vPrev. El IDOC XML se ajusta al esquema (ORDERS03.xsd) que se han generado mediante el adaptador SAP vPrev.  
  
- Un puerto de envío de archivo que se copia el IDOC en la carpeta. Este puerto también usa la canalización de ensamblador de archivo sin formato, disponible en la aplicación de BizTalk para convertir el IDOC XML en un IDOC de archivo sin formato.  
  
  Para migrar el proyecto de BizTalk vPrev existente, no es necesario cambiar el puerto de envío de archivo que se copia el IDOC de archivo sin formato en una carpeta. Deberá configurar un nuevo puerto con la configuración correcta de recepción WCF-Custom. Este tutorial muestra cómo se configura el WCF-Custom puerto de recepción para recibir los IDOC desde un sistema SAP mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para recibir un IDOC](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [Paso 2: Configurar un puerto de recepción unidireccional personalizado de WCF](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [Paso 3: Probar la aplicación migrada](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales del adaptador de SAP](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)