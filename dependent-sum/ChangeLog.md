# Revision history for dependent-sum

## 0.7.2.0 - 2022-12-22

* Update to some-1.0.4.*

## 0.7.1.1 - 2022-12-12

* Support constraints-extras 0.4

## 0.7.1.0 - 2020-03-25

* Shift version bounds for `some` to 1.0.1.* versions.

## 0.7.0.0 - 2020-03-24

* Fix ChangeLog to include the breaking change in 0.6.2.1/0.6.2.2 and properly do *major* version bump to reflect the breaking change.

## 0.6.2.2 - 2020-03-23

* Update GitHub repository in cabal metadata.

## 0.6.2.1 - 2020-03-21

* (Breaking change) Removed modules `Data.GADT.Compare`, `Data.GADT.Show`, `Data.Some` and now re-export them from the `some` package. This forced some deprecations to be fully realized.
* Update cabal meta-information (tested with GHC 8.8).

## 0.6.2.0 - 2019-08-04

* Revert change that increased strictness of Data.Some.Some in 0.6.1

## 0.6.1.0 - 2019-08-04

* Add legacy `eqTagged` and `compareTagged` functions. Fix deprecated `OrdTag` synonym (it was missing the `Has' Eq` constraint). To upgrade from dependent-sum <0.6, you will likely need to add enable the `FlexibleContexts` language extension, and possible others.

## 0.6 - 2019-03-21

* Use constraints-extras ArgDict/Has' to define the instances of Eq, Ord, Read and Show for DSum.
  This obviates the need for the EqTag, OrdTag, ReadTag and ShowTag classes.

## 0.5.1.0

* Add `mkSome` and `mapSome` to `Data.Some`.
* Add `GEq`, `GCompare`, `GShow,` and `GRead` instances for `Sum` and `Product` (Except `GRead (Product a b)`).
* Deprecate `(:=)` for `(:~:)` from `Data.Type.Equality`.
  In GHC 7.8 and above, this is the same as `(:~:)`.
  But now we no longer support earlier GHCs, so there's no point of the alias.
* Remove support for GHC 7.x.
* The git repositories for dependent-sum and dependent-sum-template are now the same, though the Haskell packages remain separate.

## 0.5.0.0

* Make `Some` a `newtype` with associated pattern synonyms using `unsafeCoerce`
  to avoid the GADT performance overhead. This shouldn't affect users.
* Deprecate the constructor name `This` in favor of `Some`.
* Drop support for GHC older than 8.0.
