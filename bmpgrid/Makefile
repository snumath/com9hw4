#---------------------------------------------------------
# 
#  Project #4: Drawing grid lines in an image in Y86-64
#
#  May 15, 2018
#
#  Jin-Soo Kim (jinsoo.kim@snu.ac.kr)
#  Systems Software & Architecture Laboratory
#  Dept. of Computer Science and Engineering
#  Seoul National University
#
#---------------------------------------------------------

CAT = /bin/cat

MISCDIR = ../misc
SEQDIR = ../seq

YAS = $(MISCDIR)/yas
SSIM = $(SEQDIR)/ssim
SSIMFLAGS = -s

TARGET	= bmptest.yo
ASRCS	= bmptest.ys
YSRCS	= bmpmain.ys bmpgrid.ys
MEMOUT  = memory.out
MEMANS  = result.out

all: $(TARGET)

$(TARGET): $(ASRCS)
	$(YAS) $(ASRCS) $@

$(ASRCS): $(YSRCS)
	$(CAT) $(YSRCS) > $(ASRCS)

clean:
	$(RM) -f $(TARGET) $(ASRCS) $(MEMOUT) *~

run: $(TARGET)
	$(SSIM) $(TARGET)

testrun: $(TARGET)
	$(SSIM) $(SSIMFLAGS) $(TARGET)

test: 
	@rm -f $(MEMOUT)
	@make testrun
	@diff $(MEMOUT) $(MEMANS) && echo "Test: SUCCESS"
