:py:mod:`astrovision.data`
==========================

.. py:module:: astrovision.data

.. autoapi-nested-parse::

   Data module.



Submodules
----------
.. toctree::
   :titlesonly:
   :maxdepth: 1

   constants/index.rst
   labeled_satellite_image/index.rst
   satellite_image/index.rst
   utils/index.rst


Package Contents
----------------

Classes
~~~~~~~

.. autoapisummary::

   astrovision.data.SatelliteImage




.. py:class:: SatelliteImage(array: numpy.array, crs: str, bounds: Tuple, transform: affine.Affine, dep: Optional[Literal[astrovision.data.constants.DEPARTMENTS_LIST]] = None, date: Optional[SatelliteImage.__init__.date] = None)


   Wrapper class for a satellite image.

   .. py:method:: split(tile_length: int) -> List[SatelliteImage]

      Split the SatelliteImage into square tiles of side `tile_length`.

      Args:
          tile_length (int): Side of of tiles.

      Returns:
          List[SatelliteImage]: List of tiles.


   .. py:method:: to_tensor(bands_indices: Optional[List[int]] = None) -> torch.Tensor

      Return SatelliteImage array as a torch.Tensor.

      Args:
          bands_indices (List): List of indices of bands to plot.
              The indices should be integers between 0 and the
              number of bands - 1.

      Returns:
          torch.Tensor: Image tensor.


   .. py:method:: normalize(quantile: float = 0.97) -> SatelliteImage

      Normalize array values with min-max normalization after
      clipping at quantiles.

      Args:
          quantile (float): Normalize an array.

      Returns:
          SatelliteImage: Normalized image.


   .. py:method:: copy() -> SatelliteImage

      Deep copy a satellite image.

      Returns:
          SatelliteImage: Copied image.


   .. py:method:: plot(bands_indices: List[int])

      Plot a subset of bands from a 3D array as an image.

      Args:
          bands_indices (List[int]): List of indices of bands to plot.
              The indices should be integers between 0 and the
              number of bands - 1.


   .. py:method:: from_raster(file_path: str, dep: Optional[Literal[astrovision.data.constants.DEPARTMENTS_LIST]] = None, date: Optional[SatelliteImage.from_raster.date] = None, n_bands: int = 3) -> SatelliteImage
      :staticmethod:

      Factory method to create a Satellite image from a raster file.

      Args:
          file_path (str): File path.
          dep (Optional[Literal[DEPARTMENTS_LIST]]): Département.
          date (Optional[date]): Date. Defaults to None.
          n_bands (int): Number of bands.

      Returns:
          SatelliteImage: Satellite image.


   .. py:method:: to_raster(file_path: str) -> None

      Save a SatelliteImage to a raster file
      according to the raster type desired (.tif or .jp2).

      Args:
          file_path (str): File path.


   .. py:method:: to_raster_jp2(file_path: str)

      Save a SatelliteImage to a .jp2 raster file.

      Args:
          file_path (str): File path.


   .. py:method:: to_raster_tif(file_path: str) -> None

      Save a SatelliteImage to a .tif raster file.

      Args:
          file_path (str): File path.



