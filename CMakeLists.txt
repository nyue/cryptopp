cmake_minimum_required(VERSION 3.12)

project(cryptopp)

# set_source_files_properties(File2.cpp PROPERTIES COMPILE_FLAGS -fno-rtti)
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c aria_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse4.1 -c blake2b_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse4.1 -c blake2s_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mavx2 -c chacha_avx.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse2 -c chacha_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c cham_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse4.2 -c crc_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse2 -c donna_sse.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -mpclmul -c gcm_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mpclmul -c gf2n_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c keccak_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c lea_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mavx2 -c lsh256_avx.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c lsh256_sse.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mavx2 -c lsh512_avx.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c lsh512_sse.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse4.1 -maes -c rijndael_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse4.2 -msha -c sha_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse4.2 -msha -c shacal2_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c simon128_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -maes -c sm4_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -mssse3 -c speck128_simd.cpp
# g++ -DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse2 -c sse_simd.cpp


# set_source_files_properties(File2.cpp PROPERTIES COMPILE_FLAGS -fno-rtti)

if (WIN32)
else()
set_source_files_properties(aria_simd.cpp PROPERTIES COMPILE_FLAGS -mssse3)
set_source_files_properties( blake2b_simd.cpp PROPERTIES COMPILE_FLAGS -msse4.1 )
set_source_files_properties( blake2s_simd.cpp PROPERTIES COMPILE_FLAGS -msse4.1 )
set_source_files_properties( chacha_avx.cpp PROPERTIES COMPILE_FLAGS -mavx2 )
set_source_files_properties( chacha_simd.cpp PROPERTIES COMPILE_FLAGS -msse2 )
set_source_files_properties( cham_simd.cpp PROPERTIES COMPILE_FLAGS -mssse3 )
set_source_files_properties( crc_simd.cpp PROPERTIES COMPILE_FLAGS -msse4.2 )
set_source_files_properties( donna_sse.cpp PROPERTIES COMPILE_FLAGS -msse2 )
set_source_files_properties( gcm_simd.cpp PROPERTIES COMPILE_FLAGS "-mssse3 -mpclmul" )
set_source_files_properties( gf2n_simd.cpp PROPERTIES COMPILE_FLAGS -mpclmul )
set_source_files_properties( keccak_simd.cpp PROPERTIES COMPILE_FLAGS -mssse3 )
set_source_files_properties( lea_simd.cpp PROPERTIES COMPILE_FLAGS -mssse3 )
set_source_files_properties( lsh256_avx.cpp PROPERTIES COMPILE_FLAGS -mavx2 )
set_source_files_properties( lsh256_sse.cpp PROPERTIES COMPILE_FLAGS -mssse3 )
set_source_files_properties( lsh512_avx.cpp PROPERTIES COMPILE_FLAGS -mavx2 )
set_source_files_properties( lsh512_sse.cpp PROPERTIES COMPILE_FLAGS -mssse3 )
set_source_files_properties( rijndael_simd.cpp PROPERTIES COMPILE_FLAGS "-msse4.1 -maes" )
set_source_files_properties( sha_simd.cpp PROPERTIES COMPILE_FLAGS "-msse4.2 -msha" )
set_source_files_properties( shacal2_simd.cpp PROPERTIES COMPILE_FLAGS "-msse4.2 -msha" )
set_source_files_properties( simon128_simd.cpp PROPERTIES COMPILE_FLAGS -mssse3 )
set_source_files_properties( sm4_simd.cpp PROPERTIES COMPILE_FLAGS "-mssse3 -maes" )
set_source_files_properties( speck128_simd.cpp PROPERTIES COMPILE_FLAGS -mssse3 )
set_source_files_properties( sse_simd.cpp PROPERTIES COMPILE_FLAGS -msse2 )
endif()

add_library(cryptopp STATIC
  
 cryptlib.cpp
 cpu.cpp
 integer.cpp
 3way.cpp
 adler32.cpp
 algebra.cpp
 algparam.cpp
 allocate.cpp
 arc4.cpp
 aria.cpp
 aria_simd.cpp
 ariatab.cpp
 asn.cpp
 authenc.cpp
 base32.cpp
 base64.cpp
 basecode.cpp
 bfinit.cpp
 blake2.cpp
 blake2b_simd.cpp
 blake2s_simd.cpp
 blowfish.cpp
 blumshub.cpp
 camellia.cpp
 cast.cpp
 casts.cpp
 cbcmac.cpp
 ccm.cpp
 chacha.cpp
 chacha_avx.cpp
 chacha_simd.cpp
 chachapoly.cpp
 cham.cpp
 cham_simd.cpp
 channels.cpp
 cmac.cpp
 crc.cpp
 crc_simd.cpp
 darn.cpp
 default.cpp
 des.cpp
 dessp.cpp
 dh.cpp
 dh2.cpp
 dll.cpp
 donna_32.cpp
 donna_64.cpp
 donna_sse.cpp
 dsa.cpp
 eax.cpp
 ec2n.cpp
 eccrypto.cpp
 ecp.cpp
 elgamal.cpp
 emsa2.cpp
 eprecomp.cpp
 esign.cpp
 files.cpp
 filters.cpp
 fips140.cpp
 fipstest.cpp
 gcm.cpp
 gcm_simd.cpp
 gf256.cpp
 gf2_32.cpp
 gf2n.cpp
 gf2n_simd.cpp
 gfpcrypt.cpp
 gost.cpp
 gzip.cpp
 hc128.cpp
 hc256.cpp
 hex.cpp
 hight.cpp
 hmac.cpp
 hrtimer.cpp
 ida.cpp
 idea.cpp
 iterhash.cpp
 kalyna.cpp
 kalynatab.cpp
 keccak.cpp
 keccak_core.cpp
 keccak_simd.cpp
 lea.cpp
 lea_simd.cpp
 lsh256.cpp
 lsh256_avx.cpp
 lsh256_sse.cpp
 lsh512.cpp
 lsh512_avx.cpp
 lsh512_sse.cpp
 luc.cpp
 mars.cpp
 marss.cpp
 md2.cpp
 md4.cpp
 md5.cpp
 misc.cpp
 modes.cpp
 mqueue.cpp
 mqv.cpp
 nbtheory.cpp
 oaep.cpp
 osrng.cpp
 padlkrng.cpp
 panama.cpp
 pkcspad.cpp
 poly1305.cpp
 polynomi.cpp
 pssr.cpp
 pubkey.cpp
 queue.cpp
 rabbit.cpp
 rabin.cpp
 randpool.cpp
 rc2.cpp
 rc5.cpp
 rc6.cpp
 rdrand.cpp
 rdtables.cpp
 rijndael.cpp
 rijndael_simd.cpp
 ripemd.cpp
 rng.cpp
 rsa.cpp
 rw.cpp
 safer.cpp
 salsa.cpp
 scrypt.cpp
 seal.cpp
 seed.cpp
 serpent.cpp
 sha.cpp
 sha3.cpp
 sha_simd.cpp
 shacal2.cpp
 shacal2_simd.cpp
 shake.cpp
 shark.cpp
 sharkbox.cpp
 simeck.cpp
 simon.cpp
 simon128_simd.cpp
 skipjack.cpp
 sm3.cpp
 sm4.cpp
 sm4_simd.cpp
 sosemanuk.cpp
 speck.cpp
 speck128_simd.cpp
 square.cpp
 squaretb.cpp
 sse_simd.cpp
 strciphr.cpp
 tea.cpp
 tftables.cpp
 threefish.cpp
 tiger.cpp
 tigertab.cpp
 ttmac.cpp
 tweetnacl.cpp
 twofish.cpp
 vmac.cpp
 wake.cpp
 whrlpool.cpp
 xed25519.cpp
 xtr.cpp
 xtrcrypt.cpp
 xts.cpp
 zdeflate.cpp
 zinflate.cpp
 zlib.cpp
 )

add_executable(cryptest
 adhoc.cpp
 test.cpp
 bench1.cpp
 bench2.cpp
 bench3.cpp
 datatest.cpp
 dlltest.cpp
 fipsalgt.cpp
 validat0.cpp
 validat1.cpp
 validat2.cpp
 validat3.cpp
 validat4.cpp
 validat5.cpp
 validat6.cpp
 validat7.cpp
 validat8.cpp
 validat9.cpp
 validat10.cpp
 regtest1.cpp
 regtest2.cpp
 regtest3.cpp
 regtest4.cpp
 )

target_link_libraries(cryptest
  cryptopp
  )
