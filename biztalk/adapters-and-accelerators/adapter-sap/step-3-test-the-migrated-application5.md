---
title: 'Paso 3: Probar el Application5 migrados | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Receive IDOC)
- migration
ms.assetid: 3ad15069-1556-4c0a-8bfd-86704d40c586
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5e49968e4b0b463b1665d0752689a14039c2da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217252"
---
# <a name="step-3-test-the-migrated-application"></a>Paso 3: Probar la aplicación migrada
![Paso 3 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, probará la aplicación migrada recibir un IDOC de archivo sin formato mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Configurar la aplicación de BizTalk mediante la asignación de los puertos lógicos de la orquestación de BizTalk a puertos físicos en la consola de administración de BizTalk Server.  
  
-   Configurar BizTalk aplicación para que use WCF-Custom puerto de recepción para basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
### <a name="to-test-the-migrated-application"></a>Para probar la aplicación migrada  
  
1.  Inicie la GUI de SAP y conéctese al sistema SAP que especificó en el URI de conexión.  
  
2.  Ejecutar SE37 e invocar un módulo de función en SAP que envía un IDOC a un sistema externo. Asegúrese de que enviar el IDOC con el mismo identificador de programa que se especifica en el URI de conexión de puerto de recepción de WCF-Custom.  
  
3.  Busque el IDOC entrante en la ubicación de archivo especificada como parte de la orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Migrar una SAP recibir IDOC proyecto de BizTalk](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)