---
title: Validar una instancia de mensaje con el esquema XSD | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50a4e0b08e3bbe9e29b3417fd6e53475fd98483c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a>Validar una instancia de mensaje con el esquema XSD
Este tema describe cómo validar una instancia de mensaje utilizando uno de los archivos de esquema XSD que Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ha integrado en el archivo de ensamblado Rnpip.  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a>Para validar una instancia de mensaje con el esquema XSD  
  
1.  Inicie **Microsoft Visual Studio 2012**.  
  
2.  En el **archivo**, seleccione **abiertos**y, a continuación, haga clic en **proyecto**.  
  
3.  Busque  *\<unidad >*\Program BizTalk \<versión > Accelerator for RosettaNet\SDK\Schemas, haga clic en **RNPIPs.btproj**y, a continuación, haga clic en **Abiertos**.  
  
4.  En el Explorador de soluciones, expanda **Rnpip**, haga clic en el esquema XSD que se desea usar para validar una instancia de mensaje y, a continuación, haga clic en **propiedades**.  
  
5.  En el cuadro de diálogo páginas de propiedades, haga clic en **nombre de archivo de instancia de entrada**, busque la carpeta que contiene el archivo, seleccione el archivo XML de instancia de mensaje y, a continuación, haga clic en **abiertos**.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el Explorador de soluciones, haga clic en el esquema XSD que se desea usar para validar una instancia de mensaje y, a continuación, haga clic en **Validar instancia**.  
  
## <a name="see-also"></a>Vea también  
 [Modificar una PIP existente en Rnpip](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)   
 [Trabajar con PIP](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)