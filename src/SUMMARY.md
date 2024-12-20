# Summary

# Overview

- [Intro](text/docsoverview.md)
- [Arrakis Protocol](text/introduction/arrakisInfra.md)
- [Brand New: HOT AMM](text/introduction/integrations/hotAmm.md)
- [Arrakis Pro](text/introduction/arrakisPro.md)

---

# Developer Docs

- [Arrakis Modular](text/arrakisModular/overview.md)

  - [Architecture](text/arrakisModular/architecture/overview.md)
    - [Meta Vaults](text/arrakisModular/architecture/metaVaults.md)
    - [Modules](text/arrakisModular/architecture/modules.md)
    - [Configuration](text/arrakisModular/architecture/configuration.md)
    - [Diagram](text/arrakisModular/architecture/diagram.md)
    - [Security](text/arrakisModular/architecture/security.md)
  - [Quickstart: Public Vaults](text/arrakisModular/quickstart.md)
  - [Public Vault List](text/arrakisModular/publicVaults.md)
  - [Price Oracles](text/arrakisModular/priceOracles.md)
  - [Deployments](text/arrakisModular/deployments.md)
  - [Technical Reference](text/arrakisModular/technicalReference/overview.md)

    - [Contracts overview](text/arrakisModular/technicalReference/contractsOverview.md)
    - [Meta Vaults](text/arrakisModular/technicalReference/metaVaults/README.md)

      - [Core](text/arrakisModular/technicalReference/metaVaults/core/README.md)
        - [ArrakisMetaVault](text/arrakisModular/technicalReference/metaVaults/core/abstract.ArrakisMetaVault.md)
        - [ArrakisMetaVaultFactory](text/arrakisModular/technicalReference/metaVaults/core/contract.ArrakisMetaVaultFactory.md)
        - [ArrakisStandardManager](text/arrakisModular/technicalReference/metaVaults/core/contract.ArrakisStandardManager.md)
      - [Public Vaults](text/arrakisModular/technicalReference/metaVaults/publicVaults/README.md)
        - [ArrakisMetaVaultPublic](text/arrakisModular/technicalReference/metaVaults/publicVaults/contract.ArrakisMetaVaultPublic.md)
        - [CreationCodePublicVault](text/arrakisModular/technicalReference/metaVaults/publicVaults/contract.CreationCodePublicVault.md)
      - [Private Vaults](text/arrakisModular/technicalReference/metaVaults/privateVaults/README.md)
        - [ArrakisMetaVaultPrivate](text/arrakisModular/technicalReference/metaVaults/privateVaults/contract.ArrakisMetaVaultPrivate.md)
        - [CreationCodePrivateVault](text/arrakisModular/technicalReference/metaVaults/privateVaults/contract.CreationCodePrivateVault.md)
        - [PrivateVaultNFT](text/arrakisModular/technicalReference/metaVaults/privateVaults/contract.PrivateVaultNFT.md)
        - [RenderController](text/arrakisModular/technicalReference/metaVaults/privateVaults/contract.RenderController.md)

    - [Modules](text/arrakisModular/technicalReference/modules/README.md)

      - [Registry](text/arrakisModular/technicalReference/modules/registry/README.md)
        - [ModuleRegistry](text/arrakisModular/technicalReference/modules/registry/abstract.ModuleRegistry.md)
        - [ModulePublicRegistry](text/arrakisModular/technicalReference/modules/registry/contract.ModulePublicRegistry.md)
        - [ModulePrivateRegistry](text/arrakisModular/technicalReference/modules/registry/contract.ModulePrivateRegistry.md)
      - [Implementations](text/arrakisModular/technicalReference/modules/implementations/README.md)
        - [ValantisModule](text/arrakisModular/technicalReference/modules/implementations/abstract.ValantisModule.md)

    - [Routers](text/arrakisModular/technicalReference/routers/README.md)

      - [ArrakisPublicVaultRouter](text/arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md)
      - [RouterSwapExecutor](text/arrakisModular/technicalReference/routers/contract.RouterSwapExecutor.md)
      - [RouterSwapResolver](text/arrakisModular/technicalReference/routers/contract.RouterSwapResolver.md)
      - [Structs](text/arrakisModular/technicalReference/routers/structs/README.md)
        - [AddLiquidityData](text/arrakisModular/technicalReference/routers/structs/struct.AddLiquidityData.md)
        - [AddLiquidityPermit2Data](text/arrakisModular/technicalReference/routers/structs/struct.AddLiquidityPermit2Data.md)
        - [RemoveLiquidityData](text/arrakisModular/technicalReference/routers/structs/struct.RemoveLiquidityData.md)
        - [RemoveLiquidityPermit2Data](text/arrakisModular/technicalReference/routers/structs/struct.RemoveLiquidityPermit2Data.md)
        - [SwapAndAddData](text/arrakisModular/technicalReference/routers/structs/struct.SwapAndAddData.md)
        - [SwapAndAddPermit2Data](text/arrakisModular/technicalReference/routers/structs/struct.SwapAndAddPermit2Data.md)
        - [SwapData](text/arrakisModular/technicalReference/routers/structs/struct.SwapData.md)

    - [Admin and Security](text/arrakisModular/technicalReference/adminAndSec/README.md)

      - [Guardian](text/arrakisModular/technicalReference/adminAndSec/contract.Guardian.md)
      - [Pauser](text/arrakisModular/technicalReference/adminAndSec/contract.Pauser.md)
      - [TimeLock](text/arrakisModular/technicalReference/adminAndSec/contract.TimeLock.md)

    - [More](text/arrakisModular/technicalReference/more/README.md)
      - [❱ abstracts](autogenerated/abstracts/README.md)
        - [ArrakisMetaVault](autogenerated/abstracts/ArrakisMetaVault.sol/abstract.ArrakisMetaVault.md)
        - [ModuleRegistry](autogenerated/abstracts/ModuleRegistry.sol/abstract.ModuleRegistry.md)
        - [ValantisModule](autogenerated/abstracts/ValantisHOTModule.sol/abstract.ValantisModule.md)
      - [❱ constants](autogenerated/constants/README.md)
        - [CArrakis constants](autogenerated/constants/CArrakis.sol/constants.CArrakis.md)
      - [❱ hooks](autogenerated/hooks/README.md)
        - [ArrakisPrivateHook](autogenerated/hooks/ArrakisPrivateHook.sol/contract.ArrakisPrivateHook.md)
      - [❱ interfaces](autogenerated/interfaces/README.md)
        - [AggregatorV3Interface](autogenerated/interfaces/AggregatorV3Interface.sol/interface.AggregatorV3Interface.md)
        - [IArrakisLPModule](autogenerated/interfaces/IArrakisLPModule.sol/interface.IArrakisLPModule.md)
        - [IArrakisLPModuleID](autogenerated/interfaces/IArrakisLPModuleID.sol/interface.IArrakisLPModuleID.md)
        - [IArrakisLPModulePrivate](autogenerated/interfaces/IArrakisLPModulePrivate.sol/interface.IArrakisLPModulePrivate.md)
        - [IArrakisLPModulePublic](autogenerated/interfaces/IArrakisLPModulePublic.sol/interface.IArrakisLPModulePublic.md)
        - [IArrakisMetaVault](autogenerated/interfaces/IArrakisMetaVault.sol/interface.IArrakisMetaVault.md)
        - [IArrakisMetaVaultFactory](autogenerated/interfaces/IArrakisMetaVaultFactory.sol/interface.IArrakisMetaVaultFactory.md)
        - [IArrakisMetaVaultPrivate](autogenerated/interfaces/IArrakisMetaVaultPrivate.sol/interface.IArrakisMetaVaultPrivate.md)
        - [IArrakisMetaVaultPublic](autogenerated/interfaces/IArrakisMetaVaultPublic.sol/interface.IArrakisMetaVaultPublic.md)
        - [IArrakisPrivateHook](autogenerated/interfaces/IArrakisPrivateHook.sol/interface.IArrakisPrivateHook.md)
        - [IArrakisPublicVaultRouter](autogenerated/interfaces/IArrakisPublicVaultRouter.sol/interface.IArrakisPublicVaultRouter.md)
        - [IArrakisStandardManager](autogenerated/interfaces/IArrakisStandardManager.sol/interface.IArrakisStandardManager.md)
        - [IBunkerModule](autogenerated/interfaces/IBunkerModule.sol/interface.IBunkerModule.md)
        - [ICreationCode](autogenerated/interfaces/ICreationCode.sol/interface.ICreationCode.md)
        - [IGuardian](autogenerated/interfaces/IGuardian.sol/interface.IGuardian.md)
        - [IHOTExecutor](autogenerated/interfaces/IHOTExecutor.sol/interface.IHOTExecutor.md)
        - [IManager](autogenerated/interfaces/IManager.sol/interface.IManager.md)
        - [IModulePrivateRegistry](autogenerated/interfaces/IModulePrivateRegistry.sol/interface.IModulePrivateRegistry.md)
        - [IModulePublicRegistry](autogenerated/interfaces/IModulePublicRegistry.sol/interface.IModulePublicRegistry.md)
        - [IModuleRegistry](autogenerated/interfaces/IModuleRegistry.sol/interface.IModuleRegistry.md)
        - [IOracleWrapper](autogenerated/interfaces/IOracleWrapper.sol/interface.IOracleWrapper.md)
        - [IOwnable](autogenerated/interfaces/IOwnable.sol/interface.IOwnable.md)
        - [IPausable](autogenerated/interfaces/IPausable.sol/interface.IPausable.md)
        - [IPauser](autogenerated/interfaces/IPauser.sol/interface.IPauser.md)
        - [IPermit2](autogenerated/interfaces/IPermit2.sol/interface.IPermit2.md)
        - [IPrivateVaultNFT](autogenerated/interfaces/IPrivateVaultNFT.sol/interface.IPrivateVaultNFT.md)
        - [IRenderController](autogenerated/interfaces/IRenderController.sol/interface.IRenderController.md)
        - [IResolver](autogenerated/interfaces/IResolver.sol/interface.IResolver.md)
        - [IRouterSwapExecutor](autogenerated/interfaces/IRouterSwapExecutor.sol/interface.IRouterSwapExecutor.md)
        - [IRouterSwapResolver](autogenerated/interfaces/IRouterSwapResolver.sol/interface.IRouterSwapResolver.md)
        - [ISovereignPool](autogenerated/interfaces/ISovereignPool.sol/interface.ISovereignPool.md)
        - [ITimeLock](autogenerated/interfaces/ITimeLock.sol/interface.ITimeLock.md)
        - [IValantisHOTModule](autogenerated/interfaces/IValantisHOTModule.sol/interface.IValantisHOTModule.md)
        - [IWETH9](autogenerated/interfaces/IWETH9.sol/interface.IWETH9.md)
      - [❱ modules](autogenerated/modules/README.md)
        - [❱ resolvers](autogenerated/modules/resolvers/README.md)
          - [ValantisResolver](autogenerated/modules/resolvers/ValantisResolver.sol/contract.ValantisResolver.md)
        - [BunkerModule](autogenerated/modules/BunkerModule.sol/contract.BunkerModule.md)
        - [HOTExecutor](autogenerated/modules/HOTExecutor.sol/contract.HOTExecutor.md)
        - [HOTOracleWrapper](autogenerated/modules/HOTOracleWrapper.sol/contract.HOTOracleWrapper.md)
        - [ValantisModulePrivate](autogenerated/modules/ValantisHOTModulePrivate.sol/contract.ValantisModulePrivate.md)
        - [ValantisModulePublic](autogenerated/modules/ValantisHOTModulePublic.sol/contract.ValantisModulePublic.md)
      - [❱ structs](autogenerated/structs/README.md)
        - [VaultInfo](autogenerated/structs/SManager.sol/struct.VaultInfo.md)
        - [SetupParams](autogenerated/structs/SManager.sol/struct.SetupParams.md)
        - [FeeIncrease](autogenerated/structs/SManager.sol/struct.FeeIncrease.md)
        - [TokenPermissions](autogenerated/structs/SPermit2.sol/struct.TokenPermissions.md)
        - [PermitTransferFrom](autogenerated/structs/SPermit2.sol/struct.PermitTransferFrom.md)
        - [SignatureTransferDetails](autogenerated/structs/SPermit2.sol/struct.SignatureTransferDetails.md)
        - [PermitBatchTransferFrom](autogenerated/structs/SPermit2.sol/struct.PermitBatchTransferFrom.md)
        - [AddLiquidityData](autogenerated/structs/SRouter.sol/struct.AddLiquidityData.md)
        - [RemoveLiquidityData](autogenerated/structs/SRouter.sol/struct.RemoveLiquidityData.md)
        - [SwapData](autogenerated/structs/SRouter.sol/struct.SwapData.md)
        - [SwapAndAddData](autogenerated/structs/SRouter.sol/struct.SwapAndAddData.md)
        - [AddLiquidityPermit2Data](autogenerated/structs/SRouter.sol/struct.AddLiquidityPermit2Data.md)
        - [RemoveLiquidityPermit2Data](autogenerated/structs/SRouter.sol/struct.RemoveLiquidityPermit2Data.md)
        - [SwapAndAddPermit2Data](autogenerated/structs/SRouter.sol/struct.SwapAndAddPermit2Data.md)
        - [SwapBalances](autogenerated/structs/SValantis.sol/struct.SwapBalances.md)
      - [❱ utils](autogenerated/utils/README.md)
        - [SVGParams](autogenerated/utils/NFTSVG.sol/struct.SVGParams.md)
        - [INFTSVG](autogenerated/utils/NFTSVG.sol/interface.INFTSVG.md)
        - [NFTSVG](autogenerated/utils/NFTSVG.sol/contract.NFTSVG.md)
        - [NFTSVGUtils](autogenerated/utils/NFTSVGUtils.sol/library.NFTSVGUtils.md)
      - [ArrakisMetaVaultFactory](autogenerated/ArrakisMetaVaultFactory.sol/contract.ArrakisMetaVaultFactory.md)
      - [ArrakisMetaVaultPrivate](autogenerated/ArrakisMetaVaultPrivate.sol/contract.ArrakisMetaVaultPrivate.md)
      - [ArrakisMetaVaultPublic](autogenerated/ArrakisMetaVaultPublic.sol/contract.ArrakisMetaVaultPublic.md)
      - [ArrakisPublicVaultRouter](autogenerated/ArrakisPublicVaultRouter.sol/contract.ArrakisPublicVaultRouter.md)
      - [ArrakisStandardManager](autogenerated/ArrakisStandardManager.sol/contract.ArrakisStandardManager.md)
      - [CreationCodePrivateVault](autogenerated/CreationCodePrivateVault.sol/contract.CreationCodePrivateVault.md)
      - [CreationCodePublicVault](autogenerated/CreationCodePublicVault.sol/contract.CreationCodePublicVault.md)
      - [Guardian](autogenerated/Guardian.sol/contract.Guardian.md)
      - [ModulePrivateRegistry](autogenerated/ModulePrivateRegistry.sol/contract.ModulePrivateRegistry.md)
      - [ModulePublicRegistry](autogenerated/ModulePublicRegistry.sol/contract.ModulePublicRegistry.md)
      - [Pauser](autogenerated/Pauser.sol/contract.Pauser.md)
      - [PrivateVaultNFT](autogenerated/PrivateVaultNFT.sol/contract.PrivateVaultNFT.md)
      - [RenderController](autogenerated/RenderController.sol/contract.RenderController.md)
      - [RouterSwapExecutor](autogenerated/RouterSwapExecutor.sol/contract.RouterSwapExecutor.md)
      - [RouterSwapResolver](autogenerated/RouterSwapResolver.sol/contract.RouterSwapResolver.md)
      - [TimeLock](autogenerated/TimeLock.sol/contract.TimeLock.md)

- [Modules](text/modules/overview.md)

  - [HOT AMM](text/modules/hotAmm/overview.md)

    - [Concepts](text/modules/hotAmm/concepts.md)
    - [Quickstart: Integrate](text/modules/hotAmm/quickstart.md)
    - [Manager Functions](text/modules/hotAmm/manager.md)
    - [Quoter](text/modules/hotAmm/quoter.md)
    - [LVR Problem](text/modules/hotAmm/problemStatement.md)
    - [Deployments](text/modules/hotAmm/deployments.md)
    - [Whitepaper](text/modules/hotAmm/whitepaper.md)

  - [Uniswap v4 Hook (Soon)](text/modules/uniV4Hook/overview.md)

---

# Resources

- [Contents](text/resources/overview.md)
- [Audits](text/resources/audits.md)
- [Research](text/resources/research.md)
- [Legacy Docs](text/resources/legacyDocs.md)
- [History](text/resources/history.md)
