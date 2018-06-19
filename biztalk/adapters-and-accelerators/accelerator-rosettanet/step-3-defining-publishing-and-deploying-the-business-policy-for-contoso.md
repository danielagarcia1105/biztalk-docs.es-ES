---
title: 'Paso 3: Definición, publicación e implementación de la directiva empresarial para Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deploying
- policies, publishing
- private process tutorial, creating policies
- policies, creating
ms.assetid: 529b16d8-226b-4046-a95d-64162ebd59a3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbdd1133145aada8b1a1abf0ccdde25547b7fed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210668"
---
# <a name="step-3-defining-publishing-and-deploying-the-business-policy-for-contoso"></a>Paso 3: Definir, publicar e implementar la directiva empresarial de Contoso
En este paso, creará una directiva empresarial que se reserva una cantidad de conjunto de unidades de cada producto que fabrica Contoso para usarse en caso de emergencia.  
  
### <a name="to-add-a-new-policy"></a>Para agregar una nueva directiva  
  
1.  En el Compositor de reglas de negocios, en el panel Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.  
  
2.  Nombre de la nueva directiva **3A2PriceAvailabilityPolicy**y, a continuación, presione **ENTRAR**.  
  
### <a name="to-add-a-policy-rule-to-enforce-the-emergency-quantity-needs"></a>Para agregar una regla de directivas para exigir la cantidad de emergencia necesita  
  
1.  Haga clic en **versión 1.0 (sin guardar)** en **3A2PriceAvailabilityPolicy**y, a continuación, haga clic en **agregar nueva regla**.  
  
2.  Nombre de la regla **Emergency proporcionar regla - cantidad agotado**y, a continuación, presione **ENTRAR**.  
  
3.  En el Compositor de reglas de negocios, en el panel derecho, haga clic en **condiciones** en el panel IF, seleccione **predicados**y, a continuación, haga clic en el **menor que o igual** predicado.  
  
4.  En el panel Explorador de hechos, expanda **vocabularios**, expanda **3A2PriceAvailabilityVocabulary**, expanda **versión 1.0 - publicada**, seleccione **cantidad Disponible**y arrástrelo hasta el `argument1` marcador de posición en la superficie del compositor.  
  
5.  Repita el paso 4 arrastrando **cantidad de emergencia necesaria** en el `argument2` marcador de posición.  
  
6.  Seleccione **Final cantidad disponible**y, a continuación, arrástrelo hasta **acciones** en el panel entonces.  
  
### <a name="to-add-a-policy-to-revise-the-number-available-field-in-the-response"></a>Para agregar una directiva para revisar el campo número disponible en la respuesta  
  
1.  Haga clic en **versión 1.0 (sin guardar)** en **3A2PriceAvailabilityPolicy**y, a continuación, haga clic en **agregar nueva regla**.  
  
2.  Nombre de la nueva regla **Emergency proporcionar regla - cantidad disponible**y, a continuación, presione **ENTRAR**.  
  
3.  En el Compositor de reglas de negocios, en el panel derecho, haga clic **condiciones** en el panel IF, seleccione **predicados**y, a continuación, haga clic en el **mayor** predicado.  
  
4.  En el panel Explorador de hechos, expanda **vocabularios**, expanda **3A2PriceAvailabilityVocabulary**, expanda **versión 1.0 - publicada**, seleccione **cantidad Disponible**y, a continuación, arrástrelo hasta el `argument1` marcador de posición en la superficie del compositor.  
  
5.  Repita el mismo paso arrastrando **cantidad de emergencia necesaria** en el `argument2` marcador de posición.  
  
6.  Seleccione **Final cantidad disponible**y, a continuación, arrástrelo hasta **acciones** en el panel entonces.  
  
7.  En el panel Explorador de hechos, expanda **versión 1.0 - publicada** en **funciones**y arrastre la `Subtract` funcionando en el **0** argumento junto a  **Última cantidad disponible** en el panel entonces.  
  
8.  Arrastre **cantidad disponible** (en **3A2PriceAvailabilityVocabulary**) y se coloca en el `value1` marcador de posición en el panel entonces.  
  
9. Arrastre **cantidad de emergencia necesaria**y colóquela en la `value2` marcador de posición en el panel entonces.  
  
### <a name="to-save-publish-and-deploy-the-business-policy"></a>Para guardar, publicar e implementar la directiva empresarial  
  
1.  En el panel Explorador de directivas, haga clic en **versión 1.0 (sin guardar)** en **3A2PriceAvailabilityPolicy**y, a continuación, haga clic en **guardar**.  
  
2.  Haga clic en ese mismo nodo y, a continuación, haga clic en **publicar**.  
  
3.  Haga clic en ese mismo nodo y, a continuación, haga clic en **implementar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Crear el proyecto HeaderHelper](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)