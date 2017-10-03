---
title: 'Paso 3: Probar el Application2 migrados | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Send IDOC)
- migration
ms.assetid: 8dc0d127-71ce-4668-a3bf-c893a8f6848d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dbf6154337dc9daf5dcfe75b3f5b7299ae843ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-migrated-application"></a>Paso 3: Probar la aplicación migrada
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada enviando un IDOC de archivo sin formato mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
-   Configurar la aplicación de BizTalk para utilizar el puerto de envío WCF-custom para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1.  En la carpeta SendIDOC_Migration, copie el archivo BOMDOC.txt. Este es el IDOC de archivo sin formato que se enviarán al sistema SAP.  
  
2.  Pegar el IDOC de archivo sin formato a la carpeta que se asigna al archivo de la ubicación de recepción.  
  
3.  La orquestación consume el archivo y envía el IDOC al sistema SAP. Compruebe si hay algún error en el Visor de eventos.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Migrar un proyecto de BizTalk SAP IDOC de envío](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)