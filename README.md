# Wildroid local_manifests

## Supported distributions

- AOSP (tag: `android-16.0.0_r2`)
- Miku UI (branch: `Blooming`, repo group: `wildroid_dep_mikuui_default`)

## How to sync the repositories

(Here we're using Miku UI as example)

1. Clone this repository to `.repo/local_manifests`

2. If the distribution is not AOSP, run the following to exclude duplicated repositories:

```
cd .repo/local_manifests
sed -i '/wildroid_dep_mikuui_default/d' .repo/local_manifests/*.xml
```

3. (Optional) Run the following to exclude kernel source repositories:

```
repo init -g default,-wildroid_kernel
```

4. Sync the tree

```
repo sync --detach
```

## How to prepare the tree for building

1. Initialize environment

```
source build/envsetup.sh
```

2. Apply Wildroid patches

```
wildroid_apply_patches
```
