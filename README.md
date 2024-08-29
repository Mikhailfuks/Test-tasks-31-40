tasks 31

import java.util.LinkedHashMap;
import java.util.Map;

public class FirstNonRepeatingCharUtil {
    public Character firstNonRepeatingChar(String str) {
        Map<Character, Integer> charCountMap = new LinkedHashMap<>();
        for (char c : str.toCharArray()) {
            charCountMap.put(c, charCountMap.getOrDefault(c, 0) + 1);
        }
        for (Map.Entry<Character, Integer> entry : charCountMap.entrySet()) {
            if (entry.getValue() == 1) {
                return entry.getKey();
            }
        }
        return null; // Возвращаем null, если все символы повторяются
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class FirstNonRepeatingCharUtilTest {
    @Test
    public void testFirstNonRepeatingChar() {
        FirstNonRepeatingCharUtil util = new FirstNonRepeatingCharUtil();
        assertEquals('w', util.firstNonRepeatingChar("swiss"));
    }

    @Test
    public void testAllRepeatingCharacters() {
        FirstNonRepeatingCharUtil util = new FirstNonRepeatingCharUtil();
        assertEquals(null, util.firstNonRepeatingChar("aabbcc"));
    }
}


tasks 32

import java.util.Arrays;

public class AnagramUtil {
    public boolean areAnagrams(String str1, String str2) {
        char[] charArray1 = str1.toLowerCase().toCharArray();
        char[] charArray2 = str2.toLowerCase().toCharArray();
        Arrays.sort(charArray1);
        Arrays.sort(charArray2);
        return Arrays.equals(charArray1, charArray2);
    }
}

import static org.junit.jupiter.api.Assertions.assertTrue;
import org.junit.jupiter.api.Test;

public class AnagramUtilTest {
    @Test
    public void testAreAnagrams() {
        AnagramUtil anagramUtil = new AnagramUtil();
        assertTrue(anagramUtil.areAnagrams("listen", "silent"));
        assertTrue(anagramUtil.areAnagrams("Triangle", "Integral"));
    }

    @Test
    public void testAreNotAnagrams() {
        AnagramUtil anagramUtil = new AnagramUtil();
        assertFalse(anagramUtil.areAnagrams("hello", "world"));
    }
}

tasks 33

public class SumUtil {
    public int sumToN(int n) {
        return n * (n + 1) / 2;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class SumUtilTest {
    @Test
    public void testSumToN() {
        SumUtil sumUtil = new SumUtil();
        assertEquals(15, sumUtil.sumToN(5)); // 1 + 2 + 3 + 4 + 5 = 15
        assertEquals(0, sumUtil.sumToN(0));  // Сумма от 1 до 0 = 0
    }
}

tasks 34

public class VowelCountUtil {
    public int countVowels(String str) {
        int count = 0;
        for (char c : str.toLowerCase().toCharArray()) {
            if ("aeiou".indexOf(c) != -1) {
                count++;
            }
        }
        return count;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class VowelCountUtilTest {
    @Test
    public void testCountVowels() {
        VowelCountUtil vowelCountUtil = new VowelCountUtil();
        assertEquals(5, vowelCountUtil.countVowels("Hello World")); // e, o, o
    }
}

tasks 35

import java.util.HashSet;
import java.util.Set;

public class CommonElementUtil {
    public Set<Integer> findCommon(int[] array1, int[] array2) {
        Set<Integer> commonElements = new HashSet<>();
        Set<Integer> set1 = new HashSet<>();
        for (int num : array1) {
            set1.add(num);
        }
        for (int num : array2) {
            if (set1

tasks 36

public class StringConcatUtil {
    public String concatenate(String str1, String str2, String str3) {
        return str1 + str2 + str3;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class StringConcatUtilTest {
    @Test
    public void testConcatenate() {
        StringConcatUtil util = new StringConcatUtil();
        assertEquals("HelloWorld!", util.concatenate("Hello", "Wor", "ld!"));
    }
}

tasks 37 

public class NumberToStringUtil {
    public String convertToString(int number) {
        return Integer.toString(number);
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class NumberToStringUtilTest {
    @Test
    public void testConvertToString() {
        NumberToStringUtil util = new NumberToStringUtil();
        assertEquals("123", util.convertToString(123));
    }

    @Test
    public void testZeroToString() {
        NumberToStringUtil util = new NumberToStringUtil();
        assertEquals("0", util.convertToString(0));
    }
}

tasks 38 

import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;

public class UniqueListUtil {
    public List<Integer> getUniqueElements(List<Integer> list) {
        return new ArrayList<>(new HashSet<>(list));
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import java.util.Arrays;
import java.util.List;
import org.junit.jupiter.api.Test;

public class UniqueListUtilTest {
    @Test
    public void testGetUniqueElements() {
        UniqueListUtil uniqueListUtil = new UniqueListUtil();
        List<Integer> result = uniqueListUtil.getUniqueElements(Arrays.asList(1, 2, 2, 3, 4, 1));
        List<Integer> expected = Arrays.asList(1, 2, 3, 4);
        assertEquals(expected, result);
    }
}

tasks 39 

public class StringUtil {
    public boolean isNullOrEmpty(String str) {
        return str == null || str.isEmpty();
    }
}

import static org.junit.jupiter.api.Assertions.assertTrue;
import org.junit.jupiter.api.Test;

public class StringUtilTest {
    @Test
    public void testIsNullOrEmpty() {
        StringUtil util = new StringUtil();
        assertTrue(util.isNullOrEmpty(null));
        assertTrue(util.isNullOrEmpty(""));
        assertFalse(util.isNullOrEmpty("hello"));
    }
}

tasks 40

public class ArraySumUtil {
    public int sum(int[] array) {
        int sum = 0;
        for (int num : array) {
            sum += num;
        }
        return sum;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class ArraySumUtilTest {
    @Test
    public void testSum() {
        ArraySumUtil arraySumUtil = new ArraySumUtil();
        assertEquals(15, arraySumUtil.sum(new int[]{1, 2, 3, 4, 5}));
    }
}
