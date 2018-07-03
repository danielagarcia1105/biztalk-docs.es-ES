---
title: Configuración CIDX las normas europeas de intercambio de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2aef1c49ca4bb87ef2e9388b9cdfcc86d2f35f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988869"
---
# <a name="setting-up-cidx-estandards-message-exchange"></a>Configuración CIDX las normas europeas de intercambio de mensajes
Este tema describe cómo configurar el intercambio de mensajes de las normas europeas de intercambio de datos química (CIDX). CIDX requiere que establezca las tres propiedades siguientes:  
  
- `Standard` propiedad en la configuración del proceso para **CIDX**  
  
- `Is Single Action` propiedad de los valores de configuración de proceso a `True`  
  
- `0A1 agreement` propiedad en el acuerdo de socio comercial a **ningún 0A1**  
  
  Para obtener información sobre las diferencias entre CIDX y RosettaNet, consulte [compatibilidad con CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).  
  
### <a name="to-set-up-cidx-message-exchange"></a>Para configurar el intercambio de mensajes CIDX  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.  
  
2. En el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3. Haga clic con el botón derecho en **Opciones de configuración de procesos**, seleccione **Nuevo**y haga clic en **Configuración de procesos**.  
  
4. En el cuadro de diálogo Propiedades de configuración de proceso nuevo, en el **General** ficha, para el **estándar** propiedad, seleccione **CIDX**.  
  
5. En el **actividad** ficha, para el **es la única acción** propiedad, seleccione **True**.  
  
6. Especifique otras opciones de configuración de proceso según sea necesario. Para obtener información sobre estas opciones, vea la tabla en [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
7. Haga clic en **Aceptar**.  
  
8. Haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **contrato**.  
  
9. En el **General**, **puertos**, **protocolo**, y **propiedades personalizadas** fichas, introduzca valores para las distintas configuraciones. Para obtener información sobre estas opciones, vea la tabla en [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
10. En el cuadro de diálogo Propiedades de nuevo contrato, en el **General** ficha, para el **0A1 acuerdo** propiedad, seleccione **ningún 0A1**.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [Creación o edición de la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [Creación o edición de un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)