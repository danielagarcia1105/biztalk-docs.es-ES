---
title: 'Paso 3: Modificar el proceso de la interfaz de socio comercial | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9640f542a55d028f3df8715c49df0e9e9ad370
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-edit-the-partner-interface-process"></a>Paso 3: Modificar el proceso de la interfaz de socio comercial
En este paso, va a editar las opciones de configuración de proceso de interfaz de socio (PIP) para deshabilitar el transporte seguro si no tiene un certificado de capa de Sockets seguros (SSL) configurado en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Internet Information Services (IIS). Dado que el escenario de bucle invertido no es compatible con la firma para los mensajes entrantes y salientes, debe cambiar la configuración predeterminada para continuar con el tutorial. Modifique el PIP STD_0C1_R01.02.  
  
### <a name="to-edit-the-std0c1r0102-pip"></a>Para editar el PIP STD_0C1_R01.02  
  
1.  En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda **BizTalk \<versión > Acelerador para RosettaNet**, haga clic en **valores de configuración de proceso**, haga clic en **STD_0C1_R01.02**y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo STD_0C1_R01.02Properties, en la **actividad** pestaña, establezca el **se requiere de transporte seguro** opción `False`. Realice este paso solo si no tiene un certificado SSL en el servidor Web de IIS.  
  
3.  Establecer el **sin repudio necesario** a `False`, establezca **se necesita autorización** a `False`, establezca **sin repudio del origen y del contenido** a `False`y, a continuación, haga clic en **Aceptar**.  
  
     Esto deshabilita sin repudio y el uso de certificados para firmar mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Crear un acuerdo comercial](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)   
 [Propiedades de autorización y sin repudio](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)