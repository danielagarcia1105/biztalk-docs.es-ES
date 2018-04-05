---
title: Normas europeas de configuración seguridad CIDX intercambio de mensajes | Documentos de Microsoft
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
ms.openlocfilehash: 4c4606dfc4b912d884a997bb65acb26cb4352448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-up-cidx-estandards-message-exchange"></a>Normas europeas de configuración seguridad CIDX intercambio de mensajes
En este tema se describe cómo configurar el intercambio de mensajes de normas europeas de intercambio de datos para la industria química (CIDX). CIDX requiere que se establezcan las tres propiedades siguientes:  
  
-   `Standard`propiedad en los valores de configuración de proceso para **CIDX**  
  
-   `Is Single Action`propiedad en las opciones de configuración de proceso`True`  
  
-   `0A1 agreement`propiedad en el acuerdo de socio comercial a **No 0A1**  
  
 Para obtener información sobre las diferencias entre CIDX y RosettaNet, consulte [CIDX compatibilidad](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).  
  
### <a name="to-set-up-cidx-message-exchange"></a>Para configurar el intercambio de mensajes CIDX  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3.  Haga clic con el botón derecho en **Opciones de configuración de procesos**, seleccione **Nuevo**y haga clic en **Configuración de procesos**.  
  
4.  En el cuadro de diálogo Propiedades de configuración de proceso nuevo, en la **General** ficha, para el **estándar** propiedad, seleccione **CIDX**.  
  
5.  En el **actividad** ficha, para el **es la única acción** propiedad, seleccione **True**.  
  
6.  Especifique otras opciones de configuración de proceso según sea necesario. Para obtener información acerca de estas opciones, vea la tabla de [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
7.  Haga clic en **Aceptar**.  
  
8.  Haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
9. En el **General**, **puertos**, **protocolo**, y **propiedades personalizadas** fichas, introduzca valores para las distintas configuraciones. Para obtener información acerca de estas opciones, vea la tabla de [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
10. En el cuadro de diálogo Propiedades del acuerdo nuevo, en la **General** ficha, para el **0A1 acuerdo** propiedad, seleccione **No 0A1**.  
  
11. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [Creación o edición de la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [Crear o editar un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)