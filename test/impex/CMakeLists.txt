IF(JPEG_FOUND)
  ADD_DEFINITIONS(-DHasJPEG)
ENDIF(JPEG_FOUND)

IF(PNG_FOUND)
  ADD_DEFINITIONS(-DHasPNG)
ENDIF(PNG_FOUND)

IF(TIFF_FOUND)
  ADD_DEFINITIONS(-DHasTIFF)
  INCLUDE_DIRECTORIES(${TIFF_INCLUDE_DIR})
ENDIF(TIFF_FOUND)

IF(OPENEXR_FOUND)
  ADD_DEFINITIONS(-DHasEXR)
ENDIF(OPENEXR_FOUND)

VIGRA_ADD_TEST(test_impex test.cxx LIBRARIES vigraimpex)

VIGRA_COPY_TEST_DATA(lenna.xv lenna_gifref.xv lennafloat.xv lennafloatrgb.xv lennargb.xv no-image.txt lenna_0.tif lenna_1.tif lenna_2.tif lenna_masked_color.tif  lenna_masked_gray.tif bilevel.tiff)

